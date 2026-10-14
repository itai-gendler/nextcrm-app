---
appliesTo:
- type: entity
  id: user-account
  effect: removes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: actions/admin/users/delete-user.ts#deleteUser
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Only admins delete users

Deleting a person happens in Administration → Users after confirmation.
