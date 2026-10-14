---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager opens the accounts list
  kind: actor
  actor: manager
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::accounts'}
- text: The Product lists every Account that is not deleted
  kind: product
  actor: manager
  entities:
  - {entity: account, effect: reads, facts: [Name, Email, Status, Assigned to, Created on]}
  contexts:
    web: {place: 'web::workspace::accounts'}
---

# List every account

## Trigger

A manager or admin opens the accounts list.

## Outcome

Every Account that is not deleted is listed.
