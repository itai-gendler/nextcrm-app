---
entities:
- entity: account
  shows: [Name, Office phone, Email, Website, Account ID, VAT number, Billing address, Shipping address, Annual revenue, Parent company, Industry, Description, Status, Assigned to, Created on]
  collects: [Name, Office phone, Email, Website, Account ID, VAT number, Billing address, Shipping address, Annual revenue, Parent company, Industry, Description, Assigned to]
- case-study
- entity: contact
  shows: [First name, Last name, Email, Mobile phone]
  collects: [First name, Last name, Position, Email, Personal email, Mobile phone, Office phone, Website, Birthday, Social profiles, Contact type, Status, Description, Account, Assigned to]
- entity: lead
  shows: [First name, Last name, Company, Email]
  collects: [First name, Last name, Company, Job title, Email, Phone, Description, Lead source, Lead status, Lead type, Referred by, Campaign, Account, Assigned to]
- entity: opportunity
  shows: [Name, Sales stage, Budget, Expected close date, Assigned to]
  collects: [Name, Expected close date, Delivery deadline, Sales type, Sales stage, Budget, Currency, Expected revenue, Next step, Description, Account, Contact, Campaign, Assigned to]
- entity: account-task
  shows: [Title, Due date, Priority, Assigned to]
  collects: [Title, Description, Due date, Priority, Assigned to]
- entity: activity
  shows: [Type, Title, Date and time, Duration, Outcome, Email subject, Notes, Created by]
  collects: [Type, Title, Date and time, Duration, Outcome, Email subject, Notes]
- entity: audit-log-entry
  shows: [Action, Changes, Changed by, Changed on]
entryPoints:
- web: /crm/accounts/{accountId}
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/accounts/[accountId]/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/accounts/[accountId]/components/BasicView.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/accounts/[accountId]/components/CaseStudyCard.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/accounts/[accountId]/components/TasksView.tsx
---

# Account

One account: its details and addresses, the case study card, its activities, similar accounts, its tasks, the contacts, opportunities and leads linked to it, and its History tab.
