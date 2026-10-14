---
kind: primary
routes:
  web: Web
steps:
- text: The User enters their email address and asks for a verification code
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product emails a six-digit code that expires after five minutes
  kind: product
  actor: user
  entities:
  - {entity: user-account, effect: reads, facts: [Email, Language]}
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The User enters the code and chooses to verify and sign in
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The code matches and the User account is Active
  kind: condition
  entities:
  - {entity: user-account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product starts a session that lasts up to seven days and opens the workspace
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
---

# Sign in with an emailed code

## Trigger

An active person wants to work in the CRM.

## Outcome

The person has a session for up to seven days and is in the workspace.

## Edge cases

- Choosing to use a different email starts over without a code.
- A Pending person who signs in sees the waiting page that lists the active admins to ask.
