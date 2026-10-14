---
appliesTo:
- type: capability
  id: delete-account
- type: capability
  id: delete-contact
- type: capability
  id: delete-lead
- type: capability
  id: delete-opportunity
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#accountReadScopeWhere
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Deleting a CRM record hides it and keeps it

Deleted accounts, contacts, leads and opportunities disappear from every list, page and search, but stay in the database until an admin restores them; nothing erases audit log entries.
