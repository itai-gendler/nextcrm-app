---
kind: primary
routes:
  web: Web
steps:
- text: The User fills in the lead form with at least a last name and chooses Create lead
  kind: actor
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::leads'}
- text: The Product creates the Lead, assigned to the chosen person or to the User
  kind: product
  actor: user
  entities:
  - {entity: lead, effect: creates, to: Current, facts: [First name, Last name, Company, Job title, Email, Phone, Description, Lead source, Lead status, Lead type, Referred by, Campaign, Account, Assigned to, Created on]}
  contexts:
    web: {place: 'web::workspace::leads'}
- text: The Product emails the assignee when it is someone else
  kind: product
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: [First name, Last name, Assigned to]}
  contexts:
    web: {place: 'web::workspace::leads'}
---

# Add a lead

## Trigger

Someone might buy.

## Outcome

The lead exists, assigned to the chosen person or to its creator; the assignee has an email when it is someone else.
