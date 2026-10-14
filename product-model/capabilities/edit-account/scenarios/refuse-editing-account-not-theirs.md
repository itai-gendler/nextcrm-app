---
kind: validation
routes:
  web: Web
steps:
- text: The User sends changes to an Account outside their records
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product refuses the change
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::account'}
---

# Refuse editing an account that is not theirs

## Trigger

A user tries to change an account they are not assigned to, did not create and do not watch.

## Outcome

Nothing changes; the User is told it is forbidden.
