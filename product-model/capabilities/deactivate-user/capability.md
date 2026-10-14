---
domain: users
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: actions/admin/users/deactivate-user.ts#deactivateUser
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Deactivate a user

Stop a person from using the CRM: they are signed out everywhere and their API tokens are revoked.
