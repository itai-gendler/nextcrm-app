---
domain: users
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: actions/admin/users/set-role.ts#setUserRole
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Set a user's role

Give a person the admin, manager or user role.
