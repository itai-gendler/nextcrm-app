---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Deactivate on another person's User account
  kind: actor
  actor: admin
  entities:
  - {entity: user-account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product makes the User account Inactive, ends all of its sessions and revokes its API tokens
  kind: product
  actor: admin
  entities:
  - {entity: user-account, effect: changes, from: Active, to: Inactive, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
---

# Deactivate an active user

## Trigger

A colleague leaves or must lose access.

## Outcome

The person is Inactive, signed out on every device, and every API token of theirs is revoked.
