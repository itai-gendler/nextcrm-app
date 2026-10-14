---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses restore on an entry whose action is Deleted, for a deal
  kind: actor
  actor: admin
  entities:
  - {entity: audit-log-entry, effect: reads, facts: [Record, Action]}
  contexts:
    web: {place: 'web::administration::audit-log'}
- text: The Product restores the Opportunity
  kind: product
  actor: admin
  entities:
  - {entity: opportunity, effect: changes, from: Deleted, to: Active, facts: []}
  contexts:
    web: {place: 'web::administration::audit-log'}
---

# Restore a deleted opportunity

## Trigger

A deal was deleted by mistake.

## Outcome

The deal is back on lists, pages and the board.

## Edge cases

- A deal deleted while marked as lost or closed comes back with that status.
