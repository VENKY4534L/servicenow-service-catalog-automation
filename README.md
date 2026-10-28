# Service Catalog and Employee Request Automation Portal

A ServiceNow portfolio implementation kit for employee service requests. It includes Catalog Item and Record Producer design, Flow Designer approval workflow guidance, ACL design, REST API integration examples, and a test plan.

**Important:** This is a project starter kit, not a preconfigured ServiceNow application. You must create and test catalog records, flows, ACLs, and REST integrations in a ServiceNow Personal Developer Instance (PDI). Adapt scripts, table names, roles, and API endpoints to your instance.

## Objectives
- Offer structured employee service request forms.
- Use Catalog Items and a Record Producer to create request records.
- Route requests for approval with Flow Designer.
- Restrict access with role-based ACLs.
- Demonstrate outbound REST integration concepts safely.
- Validate the workflow with documented test cases.

## Suggested service request examples
1. Software access request — application, business justification, required-by date.
2. Hardware request — device type, business justification, manager.
3. Employee support request — category, description, urgency.

## Setup in a ServiceNow PDI
1. Open Service Catalog and create Catalog Items using `configuration/catalog_items.md`.
2. Create a Record Producer using `configuration/record_producer.md`.
3. Build approval and fulfillment flows using `configuration/flow_designer.md`.
4. Configure roles and ACLs using `configuration/acl_design.md`.
5. Review the REST integration pattern in `scripts/rest/README.md`. Use a test endpoint or mock only.
6. Execute `test_cases/test_plan.md`, recording actual outcomes and screenshots.

## Components
- Catalog Item variable design
- Record Producer mapping guide
- Flow Designer approval/fulfillment workflow
- ACL design checklist
- RESTMessageV2 example for an outbound REST call
- Test plan with 12 scenarios

## Security and deployment
- Never commit passwords, tokens, OAuth secrets, real employee data, or production URLs.
- Use a ServiceNow Connection & Credential Alias / supported credential mechanism for real integrations; don't hard-code secrets.
- Client-side validation is not a security control.
- Test approvals, ACLs, and integration failures in a non-production instance.
- This starter kit does not create platform records automatically.

## Resume bullets (use only after implementing and testing)
**Service Catalog and Employee Request Automation Portal** | ServiceNow, Service Catalog, Flow Designer, ACLs, REST APIs
- Configured Catalog Items and a Record Producer to standardize employee service request submissions.
- Designed Flow Designer approval and fulfillment workflows with controlled status transitions and notifications.
- Applied role-based ACLs and documented an outbound REST integration pattern for secure request-data exchange.

## Project status
Implementation guide and script examples prepared. Claim completed hands-on implementation only after building and validating it in your own ServiceNow instance.
