---
type: web
actors:
- user
- manager
- admin
entryPoints:
- web: /sign-in
references:
- kind: code
  role: implementation
  target: proxy.ts
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/layout.tsx
- kind: code
  role: implementation
  target: i18n/routing.ts
---

# Web

The browser application. People sign in on the public sign-in page; signed-in people work with CRM records in the workspace; admins also reach the administration area.
