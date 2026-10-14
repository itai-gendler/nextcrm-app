---
kind: alternative
routes:
  web: Web
steps:
- text: The User enters an email address the Product does not know and asks for a verification code
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product emails a six-digit code
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The User enters the code
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product creates a Pending User account with the user role
  kind: product
  actor: user
  entities:
  - {entity: user-account, effect: creates, to: Pending, facts: [Name, Email, Language]}
  - {entity: user, effect: creates, facts: [], with: user-account}
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product emails every admin that a new User account waits for activation
  kind: product
  actor: user
  entities:
  - {entity: user-account, effect: reads, facts: [Name]}
  - {entity: admin, effect: reads, facts: []}
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product shows the waiting page with the active admins to ask
  kind: product
  actor: user
  entities:
  - {entity: user-account, effect: reads, facts: []}
  - {entity: admin, effect: reads, facts: []}
  contexts:
    web: {place: 'web::sign-in::sign-in'}
---

# Sign up with an emailed code

## Trigger

A person with no account enters their address on the sign-in page.

## Outcome

The person has a pending account, sees the waiting page, and the admins have been told by email.

## Edge cases

- When no one has an account yet, the first person to sign up becomes an active admin instead.
