---
kind: primary
routes:
  web: Web
steps:
- text: The User drags a deal of theirs to another stage's column
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: [Name, Sales stage]}
  contexts:
    web: {place: 'web::workspace::pipeline'}
- text: The Product moves the Opportunity to that Sales stage and notes when it entered it
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: changes, facts: [Sales stage, Stage entered on]}
  - {entity: sales-stage, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::pipeline'}
---

# Drag a deal to another stage

## Trigger

A deal moved forward.

## Outcome

The card sits in the new column, the person sees that the stage changed, and the deal's follow-up timing restarts from now.

## Edge cases

- Moving a deal cancels the follow-up tasks still due from its previous stage.
