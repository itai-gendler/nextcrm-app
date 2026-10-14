---
domain: approvals
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/opportunities/approval.ts#decideApproval
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/approvals/components/ApprovalsTable.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Reject a quote

Reject a deal's pending quote with a note on what must change; the rep is emailed the note.
