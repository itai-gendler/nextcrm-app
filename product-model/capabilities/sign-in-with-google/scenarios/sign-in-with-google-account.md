---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses to continue with Google
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The User picks their Google identity at Google
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Google address belongs to an Active User account
  kind: condition
  entities:
  - {entity: user-account, effect: reads, facts: [Email]}
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product starts a session and opens the workspace
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
---

# Sign in with a Google account

## Trigger

An active person prefers to sign in with Google.

## Outcome

The person has a session and is in the workspace.

## Edge cases

- Google sign-in fails with a message on the sign-in page when Google refuses or is not configured.
