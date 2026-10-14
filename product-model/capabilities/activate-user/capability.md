---
domain: users
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: actions/admin/users/activate-user.ts#activateUser
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Activate a user

Let a pending or deactivated person use the CRM; they are told by email.
