---
domain: approvals
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/opportunities/get-pending-approvals.ts
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/approvals/page.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Browse quote approvals

See the deals waiting for a quote decision, oldest request first.
