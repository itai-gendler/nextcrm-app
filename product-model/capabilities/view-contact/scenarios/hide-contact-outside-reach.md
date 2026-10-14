---
kind: validation
routes:
  web: Web
steps:
- text: The User opens a Contact that is neither theirs nor linked to a company of theirs
  kind: actor
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::contact'}
- text: The Product answers as if it did not exist
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::contact'}
---

# Hide a contact outside one's reach

## Trigger

A user opens a Contact that is not theirs.

## Outcome

The page is not found; nothing about the Contact is shown.
