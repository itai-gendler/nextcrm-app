---
kind: primary
routes:
  web: Web
steps:
- text: The User fills in the opportunity form with at least a name and saves
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunities'}
- text: The Product creates the Opportunity, Active, assigned to the chosen person or to the User, and notes when it entered its stage
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: creates, to: Active, facts: [Name, Expected close date, Delivery deadline, Sales type, Sales stage, Budget, Currency, Expected revenue, Next step, Description, Account, Contact, Campaign, Assigned to, Stage entered on, Created on]}
  contexts:
    web: {place: 'web::workspace::opportunities'}
- text: The Product emails the assignee when it is someone else
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: [Name, Assigned to]}
  contexts:
    web: {place: 'web::workspace::opportunities'}
---

# Add an opportunity

## Trigger

A sale starts to take shape.

## Outcome

The deal is Active in its stage, assigned to the chosen person or to its creator; the assignee has an email when it is someone else.

## Edge cases

- When the stage is linked to funnel automation, its follow-up starts as for a stage change.
