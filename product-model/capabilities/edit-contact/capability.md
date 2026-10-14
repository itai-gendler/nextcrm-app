---
domain: contacts
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/contacts/update-contact.ts#updateContact
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteContact
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Edit a contact

Change a contact's details, status, account or assignee.
