---
appliesTo:
- type: entity
  id: contact
  effect: changes
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: is assigned, entity: user}
- related:
  - {verb: created, entity: user}
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteContact
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Users change only the contacts assigned to them or created by them

Managers and admins change and delete any contact. A user changes and deletes only a contact assigned to them or created by them; one they see only through an account of theirs is read-only for them.
