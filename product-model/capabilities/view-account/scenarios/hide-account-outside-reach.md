---
kind: validation
routes:
  web: Web
steps:
- text: The User opens an Account that is neither theirs nor linked to a company of theirs
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product answers as if it did not exist
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::account'}
---

# Hide an account outside one's reach

## Trigger

A user opens a Account that is not theirs.

## Outcome

The page is not found; nothing about the Account is shown.
