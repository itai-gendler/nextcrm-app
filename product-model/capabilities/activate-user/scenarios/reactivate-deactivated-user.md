---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Activate on an inactive User account
  kind: actor
  actor: admin
  entities:
  - {entity: user-account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product makes the User account Active
  kind: product
  actor: admin
  entities:
  - {entity: user-account, effect: changes, from: Inactive, to: Active, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
---

# Reactivate a deactivated user

## Trigger

A deactivated colleague comes back.

## Outcome

The person is Active again; their earlier API tokens stay revoked.
