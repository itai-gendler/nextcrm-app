---
appliesTo:
- type: entity
  id: lead
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
  target: lib/authz/scopes/crm.ts#assertCanWriteLead
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Users change only the leads assigned to them or created by them

Managers and admins change and delete any lead. A user changes and deletes only a lead assigned to them or created by them; one they see only through an account of theirs is read-only for them.
