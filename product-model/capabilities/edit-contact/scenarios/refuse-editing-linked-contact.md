---
kind: validation
routes:
  web: Web
steps:
- text: The User sends changes to a Contact neither assigned to nor created by them
  kind: actor
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::contact'}
- text: The Product refuses the change
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::contact'}
---

# Refuse editing a contact seen only through an account

## Trigger

A user opens a contact they can see only because it belongs to an account of theirs.

## Outcome

Nothing changes; the contact is read-only for them.
