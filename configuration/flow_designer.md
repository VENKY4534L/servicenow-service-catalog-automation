# Flow Designer approval and fulfillment workflow

Create a flow for Catalog Item requests. Trigger and action labels vary by ServiceNow release and available plugins.

## Flow: Employee Request Approval and Fulfillment
1. Trigger when the catalog item request is submitted (select the appropriate Service Catalog trigger).
2. Read request variables and determine the approval route.
3. Ask for manager approval using the configured approval action.
4. If rejected:
   - Update the request to the appropriate rejected state.
   - Notify the requester with the rejection outcome.
   - End the flow without creating fulfillment work.
5. If approved:
   - Create or update the fulfillment task for the responsible group.
   - Set the request to the approved/in-progress state according to your process.
   - Notify the requester and assigned group.
6. Wait for fulfillment completion.
7. Update request/request item status and notify the requester.

## Suggested decision branches
- Software access → application support / access management group.
- Hardware request → hardware or asset fulfillment group.
- Employee support → route by request category.

## Guardrails
- Prevent duplicate approvals and duplicate fulfillment tasks.
- Handle cancelled requests and approval timeouts.
- Avoid sending notifications to real recipients during testing.
- Keep request status changes consistent with your instance's configured choices.
