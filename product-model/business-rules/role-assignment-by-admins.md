---
appliesTo:
- type: entity
  id: manager
  effect: creates
- type: entity
  id: admin
  effect: creates
- type: entity
  id: user
  effect: removes
- type: entity
  id: manager
  effect: removes
- type: entity
  id: admin
  effect: removes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: actions/admin/users/set-role.ts#setUserRole
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Only admins set a person's role

Roles are set in Administration → Users with Set Role.
