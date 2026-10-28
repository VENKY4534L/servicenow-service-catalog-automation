# Record Producer design

Create a Record Producer named `Employee Support Request` and map submitted variables to the approved target table in your instance.

## Suggested variables
- Request category
- Short description
- Description
- Urgency
- Requested for

## Configuration checklist
1. Choose the target table approved for your workflow (for example, a custom employee request table; do not assume Incident is always the right target).
2. Create variables and define mandatory fields.
3. Map values to the target record using the Record Producer script or field mapping options available in your release.
4. Validate input and provide a confirmation message.
5. Test that unauthorized users cannot submit requests containing restricted information.

## Illustrative script pattern

Adapt variable names and target table to your instance. Test in a PDI before use.

```javascript
// Illustrative Record Producer script pattern only.
// Use the actual variable names and target table configured in your instance.
current.short_description = producer.short_description;
current.description = producer.description;
current.category = producer.request_category;
```

The mapping above is only an example; `category` choice values and field availability depend on the target table.
