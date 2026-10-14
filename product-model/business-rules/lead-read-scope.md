---
appliesTo:
- type: entity
  id: lead
  effect: reads
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: is assigned, entity: user}
- related:
  - {verb: created, entity: user}
- related:
  - {verb: has, entity: account}
  - {verb: is assigned, entity: user}
- related:
  - {verb: has, entity: account}
  - {verb: created, entity: user}
- related:
  - {verb: has, entity: account}
  - {verb: watches, entity: user}
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#leadReadScopeWhere
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanReadLead
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Users read only the leads that are theirs or belong to an account of theirs

Managers and admins read every lead that is not deleted. A user reads a lead assigned to them or created by them, and one linked to an account they are assigned to, created or watch; any other is answered as not found.
