# Role-based ACL design

Define access according to least privilege. Roles below are examples; verify/create them according to your instance's governance.

| Resource | Employee/requester | Fulfillment agent | Request manager/admin |
|---|---|---|---|
| Submit a request | Allowed | Allowed if required | Allowed |
| Read own request | Allowed | Allowed for assigned work | Allowed per policy |
| Read all employee requests | Denied by default | Only assigned/authorized records | Allowed per approved role |
| Update fulfillment status | Denied | Allowed for assigned work | Allowed per policy |
| Delete request | Denied by default | Denied by default | Restricted administrative policy |

## Implementation checklist
- Identify the correct tables: request, requested item, task, or approved custom table.
- Configure table-level and field-level read/create/write/delete ACLs.
- Use roles and record conditions to enforce requester ownership and assignment access.
- Test with a requester, fulfillment agent, manager, and admin account.
- Keep admin access intact while testing ACLs.

This is a design checklist, not a ready-to-paste ACL script. Validate the table relationships and APIs in your instance. Hiding a field in the UI does not secure its data.
