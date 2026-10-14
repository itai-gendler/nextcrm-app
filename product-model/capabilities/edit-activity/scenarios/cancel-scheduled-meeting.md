---
kind: alternative
routes:
  web: Web
steps:
- text: The User sets a meeting they logged to Cancelled and saves
  kind: actor
  actor: user
  entities:
  - {entity: activity, effect: reads, facts: [Title]}
  contexts:
    web: {place: 'web::workspace::contact'}
- text: The Product saves the Activity as Cancelled
  kind: product
  actor: user
  entities:
  - {entity: activity, effect: changes, from: Scheduled, to: Cancelled, facts: []}
  contexts:
    web: {place: 'web::workspace::contact'}
---

# Cancel a scheduled meeting

## Trigger

A planned meeting will not happen.

## Outcome

The meeting is Cancelled; with two-way calendar sync on, the Google event is cancelled and its attendees are told.
