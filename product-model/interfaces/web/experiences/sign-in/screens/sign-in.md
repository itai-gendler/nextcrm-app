---
entities:
- entity: user-account
  collects: [Email]
entryPoints:
- web: /sign-in
references:
- kind: code
  role: implementation
  target: app/[locale]/(auth)/sign-in/components/LoginComponent.tsx
- kind: code
  role: implementation
  target: app/[locale]/(auth)/pending/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(auth)/inactive/page.tsx
---

# Sign in

Where a person asks for a one-time code by email and enters it, or continues with Google. People who are pending or inactive land on a waiting page here after signing in.
