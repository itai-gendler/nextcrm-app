---
domain: opportunities
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/opportunity-line-items/add-line-item/index.ts
- kind: code
  role: implementation
  target: lib/line-items.ts#sumLineTotals
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Add a line item

Add a product or a custom item to a deal's quote; the deal's expected revenue becomes the sum of its line totals.
