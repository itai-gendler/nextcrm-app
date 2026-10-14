---
domain: users
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: actions/admin/users/invite-user.ts#inviteUser
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Invite a user

Add a person by name, email and language; they get an active account with the user role and an invitation email.
