---
kind: edge
routes:
  web: Web
steps:
- text: The User chooses Find Similar on a lead
  kind: actor
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::lead'}
- text: The lead has not been processed by the language model yet
  kind: condition
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::lead'}
- text: The Product says it is still generating similarity data
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::lead'}
---

# Wait for similarity data

## Trigger

The record has not been processed yet, or AI is not set up.

## Outcome

The person sees that similarity data is still being generated.
