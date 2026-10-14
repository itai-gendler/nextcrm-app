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
  target: app/[locale]/(routes)/crm/dashboard/page.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# View the pipeline

See active deals as cards in one column per sales stage, and deals marked as lost in a Lost column.
