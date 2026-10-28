# Catalog Item design

Create the following items in Service Catalog. Exact form labels and available variables can vary by instance.

## Catalog Item 1: Software Access Request
- Short description: Request access to a software application
- Variables:
  - Application name (single-line text, required)
  - Access level (select box: Read, Standard, Admin; required)
  - Business justification (multi-line text, required)
  - Required-by date (date, required)
  - Manager (reference to user, required if policy demands)
- Flow: submit → manager approval → fulfillment group task → notify requester.

## Catalog Item 2: Hardware Request
- Variables:
  - Device type (select box: Laptop, Monitor, Keyboard, Other)
  - Business justification (multi-line text)
  - Required-by date (date)
  - Manager (reference to user)
- Flow: submit → manager approval → asset/IT fulfillment → notify requester.

## Catalog Item 3: Employee Support Request
- Variables:
  - Request category (select box)
  - Description (multi-line text)
  - Urgency (select box)
  - Contact preference (select box)
- Flow: submit → route by category → fulfillment task → requester updates.

For each item, provide clear instructions, mark required variables appropriately, and avoid asking for unnecessary personal or sensitive information.
