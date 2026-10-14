---
domain: opportunities
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/opportunities/update-opportunity.ts#updateOpportunity
- kind: code
  role: implementation
  target: lib/crm/approval-gate.ts#qualifiedEntryBlockReason
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteOpportunity
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Edit an opportunity

Change a deal's details, including its sales stage, account and assignee. Saving a deal makes it Active.
