---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses the plus icon in a stage's column header and fills in the opportunity form
  kind: actor
  actor: user
  entities:
  - {entity: sales-stage, effect: reads, facts: [Name]}
  - {entity: opportunity, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::pipeline'}
- text: The Product creates the Opportunity, Active, in that Sales stage
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: creates, to: Active, facts: [Name, Expected close date, Delivery deadline, Sales type, Sales stage, Budget, Currency, Expected revenue, Next step, Description, Account, Contact, Campaign, Assigned to, Stage entered on, Created on]}
  - {entity: sales-stage, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::pipeline'}
---

# Add a deal in a pipeline column

## Trigger

The person is on the pipeline board and adds a deal straight into a stage.

## Outcome

The new deal is a card in that stage's column.
