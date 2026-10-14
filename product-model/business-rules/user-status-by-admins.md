---
appliesTo:
- type: entity
  id: user-account
  effect: changes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: actions/admin/users/activate-user.ts#activateUser
- kind: code
  role: implementation
  target: actions/admin/users/deactivate-user.ts#deactivateUser
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Only admins activate or deactivate users

Activation and deactivation happen in Administration → Users.
