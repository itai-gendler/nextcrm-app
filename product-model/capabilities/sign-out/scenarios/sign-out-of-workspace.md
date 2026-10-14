---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses to log out
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace'}
- text: The Product ends the session
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace'}
---

# Sign out of the workspace

## Trigger

The person is done working.

## Outcome

The session ends and the sign-in page is shown.
