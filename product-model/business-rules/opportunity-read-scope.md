---
appliesTo:
- type: entity
  id: opportunity
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
- unattended: true
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#opportunityReadScopeWhere
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanReadOpportunity
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Users read only the opportunities that are theirs or belong to an account of theirs

Managers and admins read every opportunity that is not deleted. A user reads a opportunity assigned to them or created by them, and one linked to an account they are assigned to, created or watch; any other is answered as not found.
