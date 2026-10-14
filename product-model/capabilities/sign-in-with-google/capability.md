---
domain: users
availability:
- {place: 'web::sign-in'}
references:
- kind: code
  role: implementation
  target: lib/auth.ts
- kind: code
  role: implementation
  target: app/[locale]/(auth)/sign-in/components/LoginComponent.tsx
- kind: code
  role: implementation
  target: lib/auth-server.ts#getSession
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/getting-started.mdx
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Sign in with Google

Get into NextCRM with a Google account, where the instance has Google sign-in configured. A Google address the Product does not know signs the person up, pending an admin's approval.
