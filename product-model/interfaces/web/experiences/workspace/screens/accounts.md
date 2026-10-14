---
entities:
- entity: account
  shows: [Name, Email, Status, Assigned to, Created on, Watchers]
  collects: [Name, Office phone, Email, Website, Account ID, VAT number, Billing address, Shipping address, Annual revenue, Parent company, Industry, Description, Assigned to]
entryPoints:
- web: /crm/accounts
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/accounts/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/accounts/table-components/columns.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/accounts/table-components/data-table-row-actions.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/accounts/components/NewAccountForm.tsx
---

# Companies

The list of accounts the person may see, with filters by name and status, and the side panels to add or update an account.
