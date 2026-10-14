---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses the pencil icon on a call they logged, sets Completed, fills in the outcome and saves
  kind: actor
  actor: user
  entities:
  - {entity: activity, effect: reads, facts: [Title]}
  contexts:
    web: {place: 'web::workspace::contact'}
- text: The Product saves the Activity as Completed
  kind: product
  actor: user
  entities:
  - {entity: activity, effect: changes, from: Scheduled, to: Completed, facts: [Outcome]}
  contexts:
    web: {place: 'web::workspace::contact'}
---

# Complete a scheduled call

## Trigger

A planned call happened.

## Outcome

The call is Completed with its outcome.
