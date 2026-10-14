---
kind: validation
routes:
  web: Web
steps:
- text: The Admin chooses Delete on their own User account
  kind: actor
  actor: admin
  entities:
  - {entity: user-account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product refuses
  kind: product
  actor: admin
  entities: []
  contexts:
    web: {place: 'web::administration::users'}
---

# Refuse deleting oneself

## Trigger

An admin tries to delete their own account.

## Outcome

Nothing changes; the admin is told they cannot delete themselves.
