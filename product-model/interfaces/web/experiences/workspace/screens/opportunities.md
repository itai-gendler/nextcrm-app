---
entities:
- entity: opportunity
  shows: [Name, Account, Assigned to, Budget, Expected close date, Next step]
  collects: [Name, Expected close date, Delivery deadline, Sales type, Sales stage, Budget, Currency, Expected revenue, Next step, Description, Account, Contact, Campaign, Assigned to]
entryPoints:
- web: /crm/opportunities
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/opportunities/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/opportunities/table-components/columns.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/opportunities/table-components/data-table-row-actions.tsx
---

# Opportunities

The list of opportunities the person may see, filtered by name and status, with the side panels to add or update an opportunity.
