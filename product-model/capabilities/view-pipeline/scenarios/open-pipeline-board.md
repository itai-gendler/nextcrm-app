---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the Dashboard
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::pipeline'}
- text: The Product shows the Sales stages as columns with the active Opportunities in each and the inactive ones under Lost
  kind: product
  actor: user
  entities:
  - {entity: sales-stage, effect: reads, facts: [Name, Order]}
  - {entity: opportunity, effect: reads, facts: [Name, Sales stage, Account, Budget, Expected close date, Assigned to]}
  contexts:
    web: {place: 'web::workspace::pipeline'}
---

# Open the pipeline board

## Trigger

The person opens Sales → Dashboard.

## Outcome

Each sales stage has a column of its active deals; deals marked as lost are in the Lost column.

## Edge cases

- Closed and deleted deals are not on the board.
