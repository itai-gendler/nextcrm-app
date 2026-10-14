---
kind: validation
routes:
  web: Web
steps:
- text: The User opens a Lead that is neither theirs nor linked to a company of theirs
  kind: actor
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::lead'}
- text: The Product answers as if it did not exist
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::lead'}
---

# Hide a lead outside one's reach

## Trigger

A user opens a Lead that is not theirs.

## Outcome

The page is not found; nothing about the Lead is shown.
