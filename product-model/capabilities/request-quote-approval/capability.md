---
domain: opportunities
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/opportunities/approval.ts#requestApproval
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/opportunities/[opportunityId]/components/RequestApprovalButton.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Request quote approval

Ask the managers and admins to sign off a deal's quote or statement of work before it goes to the client.
