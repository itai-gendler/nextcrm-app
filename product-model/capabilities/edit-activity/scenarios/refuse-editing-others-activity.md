---
kind: validation
routes:
  web: Web
steps:
- text: The User saves changes to an Activity they did not log
  kind: actor
  actor: user
  entities:
  - {entity: activity, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::contact'}
- text: The Product refuses the change
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::contact'}
---

# Refuse editing someone else's activity

## Trigger

A user edits an activity another person logged.

## Outcome

Nothing changes; the User is told it is forbidden.
