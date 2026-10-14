---
kind: primary
routes:
  web: Web
steps:
- text: The Admin opens the Audit Log and picks an entity, an action and a date range
  kind: actor
  actor: admin
  entities: []
  contexts:
    web: {place: 'web::administration::audit-log'}
- text: The Product lists the matching Audit log entries, newest first
  kind: product
  actor: admin
  entities:
  - {entity: audit-log-entry, effect: reads, facts: [Record, Action, Changes, Changed by, Changed on]}
  contexts:
    web: {place: 'web::administration::audit-log'}
---

# Filter the audit log

## Trigger

An admin investigates a change.

## Outcome

The admin sees the matching entries, newest first, 50 to a page.

## Edge cases

- With all entities selected, entries from other parts of the system, such as plugin installs and setting changes, are listed too.
