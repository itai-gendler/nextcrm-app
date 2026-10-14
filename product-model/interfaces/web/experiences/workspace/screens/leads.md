---
entities:
- entity: lead
  shows: [First name, Last name, Company, Email, Phone, Lead status, Assigned to, Created on]
  collects: [First name, Last name, Company, Job title, Email, Phone, Description, Lead source, Lead status, Lead type, Referred by, Campaign, Account, Assigned to]
entryPoints:
- web: /crm/leads
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/leads/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/leads/table-components/columns.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/leads/table-components/data-table-row-actions.tsx
---

# Leads

The list of leads the person may see, filtered by company and status, with the side panels to add or update a lead.
