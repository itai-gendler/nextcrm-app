---
domain: contacts
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/get-contact.ts
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanReadContact
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/accounts-contacts.mdx
---

# View a contact

Open one Contact's page with its details and everything linked to it.
