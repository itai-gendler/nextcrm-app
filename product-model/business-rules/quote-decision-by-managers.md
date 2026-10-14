---
appliesTo:
- type: entity
  id: quote-approval
  effect: changes
  from: Pending
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: actions/crm/opportunities/approval.ts#decideApproval
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/approvals/page.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Only managers and admins decide a quote approval

Approving or rejecting a pending quote is open to managers and admins only; people with the user role do not see the approvals queue.
