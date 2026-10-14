---
appliesTo:
- type: entity
  id: user-account
  effect: creates
  to: Active
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: actions/admin/users/invite-user.ts#inviteUser
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Only admins invite users

Inviting creates an active account with the user role at once, so it is reserved to admins.
