---
appliesTo:
- type: entity
  id: opportunity
  effect: changes
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: is assigned, entity: user}
- related:
  - {verb: created, entity: user}
- unattended: true
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteOpportunity
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Users change only the opportunities assigned to them or created by them

Managers and admins change and delete any opportunity. A user changes and deletes only a opportunity assigned to them or created by them; one they see only through an account of theirs is read-only for them. The Product's own daily check closes silent deals.
