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
  target: actions/crm/opportunities/update-opportunity.ts#updateOpportunity
- kind: code
  role: implementation
  target: lib/crm/stage-transition.ts#handleStageTransition
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Change an opportunity's sales stage

Move a deal to another stage by dragging its card on the pipeline board.
