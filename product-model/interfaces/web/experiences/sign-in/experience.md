---
actors:
- user
access: public
references:
- kind: code
  role: implementation
  target: proxy.ts
- kind: code
  role: implementation
  target: app/[locale]/(auth)/sign-in/components/LoginComponent.tsx
---

# Sign in

The pages reached without a session: signing in with an email code or Google, and the waiting pages shown to people who are not active yet.
