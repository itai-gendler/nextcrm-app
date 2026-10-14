---
entities:
- entity: account-task
  shows: [Title, Due date, Priority]
- entity: lead
  shows: [First name, Last name, Company, Lead status]
- entity: opportunity
  shows: [Name, Sales stage, Budget, Expected close date]
entryPoints:
- web: /crm/dashboard/user
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/dashboard/user/page.tsx
---

# My Dashboard

The signed-in person's own open tasks, leads and active opportunities.
