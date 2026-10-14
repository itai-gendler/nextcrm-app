---
entities:
- entity: opportunity
  shows: [Name, Sales stage, Account, Budget, Expected close date, Assigned to]
  collects: [Name, Expected close date, Delivery deadline, Sales type, Sales stage, Budget, Currency, Expected revenue, Next step, Description, Account, Contact, Campaign, Assigned to]
- entity: sales-stage
  shows: [Name]
entryPoints:
- web: /crm/dashboard
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/dashboard/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/dashboard/_components/CRMKanban.tsx
---

# Dashboard

The pipeline board under Sales: active opportunities as cards in one column per sales stage, and a Lost column of inactive deals.
