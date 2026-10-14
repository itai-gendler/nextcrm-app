---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses restore on an entry whose action is Deleted, for a company
  kind: actor
  actor: admin
  entities:
  - {entity: audit-log-entry, effect: reads, facts: [Record, Action]}
  contexts:
    web: {place: 'web::administration::audit-log'}
- text: The Product restores the Account
  kind: product
  actor: admin
  entities:
  - {entity: account, effect: changes, from: Deleted, to: Current, facts: []}
  contexts:
    web: {place: 'web::administration::audit-log'}
---

# Restore a deleted account

## Trigger

An account was deleted by mistake.

## Outcome

The account is back in lists and pages, and a Restored entry is in the log.
