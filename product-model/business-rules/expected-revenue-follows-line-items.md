---
appliesTo:
- type: capability
  id: add-line-item
- type: capability
  id: edit-line-item
- type: capability
  id: remove-line-item
references:
- kind: code
  role: implementation
  target: lib/line-items.ts#sumLineTotals
- kind: code
  role: implementation
  target: actions/crm/opportunity-line-items/add-line-item/index.ts
---

# A deal's expected revenue is the sum of its line totals

Adding or changing a line item sets the deal's expected revenue to the sum of all its line totals; removing one sets it to the sum of the rest.
