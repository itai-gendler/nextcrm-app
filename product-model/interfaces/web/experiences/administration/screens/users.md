---
entities:
- entity: user-account
  shows: [Name, Email, Language, Last login]
  collects: [Name, Email, Language]
entryPoints:
- web: /admin/users
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/users/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/users/table-components/data-table-row-actions.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/users/components/IviteForm.tsx
---

# Users

Every person with access, their status and role, the invitation form and each person's row actions.
