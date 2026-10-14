---
kind: validation
routes:
  web: Web
steps:
- text: The User saves a line item with a percentage discount above 100
  kind: actor
  actor: user
  entities:
  - {entity: line-item, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product refuses the Line item
  kind: product
  actor: user
  entities:
  - {entity: line-item, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Refuse a percentage discount over 100%

## Trigger

The person enters a percentage discount above 100.

## Outcome

Nothing is added; the person is told the discount cannot exceed 100%.
