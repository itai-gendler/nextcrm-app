---
domain: dashboard
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/dashboard/_components/CRMKanban.tsx
- kind: code
  role: implementation
  target: actions/crm/opportunity/dashboard/set-inactive.ts#setInactiveOpportunity
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Mark an opportunity as lost

Take a deal off its stage and into the Lost column.
