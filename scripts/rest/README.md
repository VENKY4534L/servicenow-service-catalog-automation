# Outbound REST API integration pattern

Use a test endpoint or mock service in development. For production integrations, configure ServiceNow Connection & Credential Alias / supported credential storage and never hard-code secrets.

## Example: RESTMessageV2 pattern

Create an outbound REST Message and HTTP method in ServiceNow, then call it from an approved server-side script. This example assumes a REST Message named `Employee Request Integration` and method `create_request` already exist in the instance.

```javascript
(function executeIntegration(requestPayload) {
    var request = new sn_ws.RESTMessageV2(
        'Employee Request Integration',
        'create_request'
    );
    request.setRequestHeader('Accept', 'application/json');
    request.setRequestHeader('Content-Type', 'application/json');
    request.setRequestBody(JSON.stringify(requestPayload));

    try {
        var response = request.execute();
        var status = response.getStatusCode();
        var body = response.getBody();

        gs.info('Employee request integration HTTP status: ' + status);
        // Parse and validate the response before updating any records.
        return {
            status: status,
            body: body
        };
    } catch (ex) {
        gs.error('Employee request integration failed: ' + ex.message);
        throw ex;
    }
})({
    request_number: 'DEMO-REQUEST-001',
    request_type: 'software_access'
});
```

## Before using this pattern
- Create the REST Message and method in your own instance.
- Configure authentication with supported credential storage.
- Set connection timeouts and handle non-2xx HTTP status codes.
- Validate and sanitize payload fields; do not transmit unnecessary employee data.
- Avoid logging secrets or sensitive payloads.
- Test network failures, invalid responses, and retry behavior.
