---
kind: validation
routes:
  web: Web
steps:
- text: The User enters a code that does not match or has expired
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product refuses the code and keeps the User on the sign-in page
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
---

# Refuse a wrong or expired code

## Trigger

The person enters a code that does not match or is older than five minutes.

## Outcome

No session starts; the page says the code is invalid or expired.
