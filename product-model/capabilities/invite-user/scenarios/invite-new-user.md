---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters a name, an email address and a language and sends the invitation
  kind: actor
  actor: admin
  entities: []
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product creates an Active User account with the user role
  kind: product
  actor: admin
  entities:
  - {entity: user-account, effect: creates, to: Active, facts: [Name, Email, Language]}
  - {entity: user, effect: creates, facts: [], with: user-account}
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product emails the invitation to the new User account's address
  kind: product
  actor: admin
  entities:
  - {entity: user-account, effect: reads, facts: [Email, Language]}
  contexts:
    web: {place: 'web::administration::users'}
---

# Invite a new user

## Trigger

An admin wants a colleague to start using the CRM.

## Outcome

The colleague has an Active account with the user role and an invitation email in their language.
