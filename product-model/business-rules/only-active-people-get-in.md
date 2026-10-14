---
appliesTo:
- type: capability
  id: sign-in-with-email-code
- type: capability
  id: sign-in-with-google
references:
- kind: code
  role: implementation
  target: lib/auth-server.ts#getSession
- kind: code
  role: implementation
  target: app/[locale]/(auth)/pending/page.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# Only active people use the CRM

A pending or inactive person who signs in sees a waiting or inactive page; every page, action and API treats them as signed out, and their API tokens are refused.
