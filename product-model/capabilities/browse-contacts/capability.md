---
domain: contacts
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/get-contacts.ts
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#contactReadScopeWhere
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Browse contacts

List the contacts one may see, newest first, filtered by last name and by status.
