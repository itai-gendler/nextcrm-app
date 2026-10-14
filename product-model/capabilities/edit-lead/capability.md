---
domain: leads
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/leads/update-lead.ts#updateLead
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteLead
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Edit a lead

Change a lead's details, status, source, account or assignee.
