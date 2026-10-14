---
kind: validation
routes:
  web: Web
steps:
- text: The User chooses Request approval
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The deal's Quote approval is Pending or Approved
  kind: condition
  entities:
  - {entity: quote-approval, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product refuses the request
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Refuse a request while one is pending or approved

## Trigger

Approval is already pending, or already given.

## Outcome

Nothing changes; the person is told approval is already pending or the deal is already approved.
