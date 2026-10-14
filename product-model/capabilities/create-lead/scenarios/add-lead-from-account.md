---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses + on the account's Leads card and fills in the lead form
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  - {entity: lead, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product creates the Lead linked to the Account
  kind: product
  actor: user
  entities:
  - {entity: lead, effect: creates, to: Current, facts: [First name, Last name, Company, Job title, Email, Phone, Description, Lead source, Lead status, Lead type, Referred by, Campaign, Account, Assigned to, Created on]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Add a lead from an account page

## Trigger

The person is on a company's page and records a new lead there.

## Outcome

The lead is linked to the account and appears on its Leads card.
