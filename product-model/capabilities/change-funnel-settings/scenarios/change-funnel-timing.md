---
kind: primary
routes:
  web: Web
steps:
- text: The Admin changes the timing values and saves
  kind: actor
  actor: admin
  entities:
  - {entity: funnel-settings, effect: reads, facts: [Silent deal limit, Follow-up cadence, Care check-in delay, Referral ask delay, Quarterly check-in interval, Quarterly check-in count, Renewal window, Recycle delay]}
  contexts:
    web: {place: 'web::administration::funnel-settings'}
- text: The Product saves the Funnel settings
  kind: product
  actor: admin
  entities:
  - {entity: funnel-settings, effect: changes, facts: [Silent deal limit, Follow-up cadence, Care check-in delay, Referral ask delay, Quarterly check-in interval, Quarterly check-in count, Renewal window, Recycle delay]}
  contexts:
    web: {place: 'web::administration::funnel-settings'}
---

# Change the funnel timing

## Trigger

The team wants a different rhythm.

## Outcome

The new timing applies to deals that enter a stage from now on.

## Edge cases

- Cadences already running keep the timing they started with.
