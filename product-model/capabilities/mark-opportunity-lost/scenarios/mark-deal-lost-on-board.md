---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses the thumbs-down icon on a deal's card
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::pipeline'}
- text: The Product makes the Opportunity Inactive
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: changes, from: Active, to: Inactive, facts: []}
  contexts:
    web: {place: 'web::workspace::pipeline'}
---

# Mark a deal as lost on the board

## Trigger

The client said no.

## Outcome

The deal is Inactive and shown under Lost.
