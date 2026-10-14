---
kind: validation
routes:
  web: Web
steps:
- text: The User opens an Opportunity that is neither theirs nor linked to a company of theirs
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product answers as if it did not exist
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Hide an opportunity outside one's reach

## Trigger

A user opens a Opportunity that is not theirs.

## Outcome

The page is not found; nothing about the Opportunity is shown.
