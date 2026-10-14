---
kind: validation
routes:
  web: Web
steps:
- text: The Admin sets their own role to manager or user
  kind: actor
  actor: admin
  entities:
  - {entity: manager, effect: reads, facts: []}
  - {entity: user, effect: reads, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product refuses
  kind: product
  actor: admin
  entities: []
  contexts:
    web: {place: 'web::administration::users'}
---

# Refuse removing one's own admin role

## Trigger

An admin tries to give themselves a lower role.

## Outcome

Nothing changes; the admin is told they cannot remove their own admin role.
