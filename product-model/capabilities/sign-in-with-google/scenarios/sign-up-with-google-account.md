---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses to continue with Google and picks their Google identity
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product creates a Pending User account with the user role from the Google profile
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
---

# Sign up with a Google account

## Trigger

A person whose Google address has no account continues with Google.

## Outcome

The person has a pending account and sees the waiting page; the admins are told by email.
