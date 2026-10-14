---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Delete on another person's User account and confirms
  kind: actor
  actor: admin
  entities:
  - {entity: user-account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product removes the User account
  kind: product
  actor: admin
  entities:
  - {entity: user-account, effect: removes, from: Active}
  - {entity: user, effect: removes, with: user-account}
  contexts:
    web: {place: 'web::administration::users'}
---

# Delete another user

## Trigger

An account is no longer needed.

## Outcome

The person's account is gone.
