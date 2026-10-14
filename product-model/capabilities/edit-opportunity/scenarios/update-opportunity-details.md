---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Update on a deal of theirs, changes fields and saves
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product saves the Opportunity's new details and, when the stage changed, notes when it entered the new one
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: changes, facts: [Name, Expected close date, Delivery deadline, Sales type, Sales stage, Budget, Currency, Expected revenue, Next step, Description, Account, Contact, Campaign, Assigned to, Stage entered on]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Update an opportunity's details

## Trigger

The deal moves on or its numbers change.

## Outcome

The deal shows the new details and its history lists the changes; a stage change restarts its follow-up timing.
