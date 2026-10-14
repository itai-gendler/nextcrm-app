---
domain: leads
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/get-lead.ts
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanReadLead
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# View a lead

Open one Lead's page with its details and everything linked to it.
