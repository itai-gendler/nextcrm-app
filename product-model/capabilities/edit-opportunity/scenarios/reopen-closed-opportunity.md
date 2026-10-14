---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens a Closed deal from the link in the closing email and saves it
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product saves the Opportunity as Active
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: changes, from: Closed, to: Active, facts: [Name, Expected close date, Delivery deadline, Sales type, Sales stage, Budget, Currency, Expected revenue, Next step, Description, Account, Contact, Campaign, Assigned to]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Reopen a closed opportunity

## Trigger

A deal closed by the silence rule turns out to be alive.

## Outcome

The deal is Active again and back on the pipeline board.

## Edge cases

- Saving a deal marked as lost makes it Active again in the same way.
