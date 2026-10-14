---
entities:
- entity: opportunity
  shows: [Name, Account, Assigned to, Budget]
- entity: quote-approval
  shows: [Requested on]
  collects: [Note]
entryPoints:
- web: /crm/approvals
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/approvals/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/approvals/components/ApprovalsTable.tsx
---

# Quote approvals

The queue of deals waiting for a quote decision, oldest request first, for managers and admins.
