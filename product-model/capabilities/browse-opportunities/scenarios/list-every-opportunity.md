---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager opens the opportunities list
  kind: actor
  actor: manager
  entities:
  - {entity: opportunity, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunities'}
- text: The Product lists every Opportunity that is not deleted
  kind: product
  actor: manager
  entities:
  - {entity: opportunity, effect: reads, facts: [Name, Account, Assigned to, Budget, Expected close date, Next step]}
  contexts:
    web: {place: 'web::workspace::opportunities'}
---

# List every opportunity

## Trigger

A manager or admin opens the opportunities list.

## Outcome

Every Opportunity that is not deleted is listed.
