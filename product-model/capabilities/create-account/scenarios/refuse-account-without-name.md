---
kind: validation
routes:
  web: Web
steps:
- text: The User chooses Create account with no name
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::accounts'}
- text: The Product refuses and marks the missing name
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::accounts'}
---

# Refuse an account without a name

## Trigger

The form is sent without an account name.

## Outcome

No account is created; the form says the name is missing.
