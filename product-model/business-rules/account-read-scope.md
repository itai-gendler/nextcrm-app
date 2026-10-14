---
appliesTo:
- type: entity
  id: account
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
  - {verb: watches, entity: user}
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#accountReadScopeWhere
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanReadAccount
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Users read only the accounts assigned to them, created by them or watched by them

Managers and admins read every account that is not deleted. A user reads an account they are assigned to, created or watch; any other account is answered as not found.
