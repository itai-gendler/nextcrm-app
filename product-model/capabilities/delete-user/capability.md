---
domain: users
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: actions/admin/users/delete-user.ts#deleteUser
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Delete a user

Remove a person's account after confirmation.
