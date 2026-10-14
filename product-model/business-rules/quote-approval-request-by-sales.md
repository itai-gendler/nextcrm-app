---
appliesTo:
- type: entity
  id: quote-approval
  effect: creates
- type: entity
  id: quote-approval
  effect: changes
  from: Rejected
permits:
- actors:
  - user
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: actions/crm/opportunities/approval.ts#requestApproval
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Salespeople, managers and admins request quote approval

Requesting approval, and requesting it again after a rejection, is done from the deal page.
