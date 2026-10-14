---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses the trash icon on an activity they logged and confirms Delete
  kind: actor
  actor: user
  entities:
  - {entity: activity, effect: reads, facts: [Title]}
  contexts:
    web: {place: 'web::workspace::lead'}
- text: The Product removes the Activity
  kind: product
  actor: user
  entities:
  - {entity: activity, effect: removes, from: Scheduled}
  contexts:
    web: {place: 'web::workspace::lead'}
---

# Delete an activity from a feed

## Trigger

An activity was logged by mistake.

## Outcome

The activity is gone from every feed it was in.

## Edge cases

- A meeting synced to the person's Google Calendar is cancelled there too, and its attendees are told.
