---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Update on a lead of theirs, changes fields and saves
  kind: actor
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::lead'}
- text: The Product saves the Lead's new details
  kind: product
  actor: user
  entities:
  - {entity: lead, effect: changes, facts: [First name, Last name, Company, Job title, Email, Phone, Description, Lead source, Lead status, Lead type, Referred by, Campaign, Account, Assigned to]}
  contexts:
    web: {place: 'web::workspace::lead'}
- text: The Product emails the assignee when it is someone other than the User
  kind: product
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: [Assigned to]}
  contexts:
    web: {place: 'web::workspace::lead'}
---

# Update a lead's details

## Trigger

The person learns more about the lead or moves it on.

## Outcome

The lead shows the new details; a newly assigned person has an email.

## Edge cases

- Saving with no assignee assigns the lead to the person saving it.
