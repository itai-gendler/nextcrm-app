---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the History tab of an account they may see
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product lists the account's Audit log entries, newest first, 25 at a time
  kind: product
  actor: user
  entities:
  - {entity: audit-log-entry, effect: reads, facts: [Action, Changes, Changed by, Changed on]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Read an account's history

## Trigger

The person wants to know who changed what.

## Outcome

The person sees each change, newest first, with who made it, when, a badge for the action and each field's old and new value.
