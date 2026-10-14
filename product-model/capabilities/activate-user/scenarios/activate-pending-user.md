---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Activate on a pending User account
  kind: actor
  actor: admin
  entities:
  - {entity: user-account, effect: reads, facts: [Name, Email]}
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product makes the User account Active
  kind: product
  actor: admin
  entities:
  - {entity: user-account, effect: changes, from: Pending, to: Active, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product emails the person that they may now sign in
  kind: product
  actor: admin
  entities:
  - {entity: user-account, effect: reads, facts: [Email, Language]}
  contexts:
    web: {place: 'web::administration::users'}
---

# Activate a pending user

## Trigger

Someone signed up and an admin approves them.

## Outcome

The person is Active and receives an email saying so.
