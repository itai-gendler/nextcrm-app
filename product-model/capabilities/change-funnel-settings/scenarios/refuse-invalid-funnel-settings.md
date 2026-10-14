---
kind: validation
routes:
  web: Web
steps:
- text: The Admin saves a value out of range
  kind: actor
  actor: admin
  entities: []
  contexts:
    web: {place: 'web::administration::funnel-settings'}
- text: The Product refuses the settings
  kind: product
  actor: admin
  entities: []
  contexts:
    web: {place: 'web::administration::funnel-settings'}
---

# Refuse timing out of range

## Trigger

A value is not a whole number of days from 1 to 365, or the quarterly count is not 0 to 24.

## Outcome

Nothing is saved; the admin is told the values are invalid.
