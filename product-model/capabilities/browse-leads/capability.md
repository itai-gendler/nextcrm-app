---
domain: leads
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/get-leads.ts
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#leadReadScopeWhere
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Browse leads

List the leads one may see, newest first, filtered by company and by status.
