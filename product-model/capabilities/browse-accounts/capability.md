---
domain: companies
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/get-accounts.ts
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#accountReadScopeWhere
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Browse accounts

List the accounts one may see, newest first, filtered by name and by status.
