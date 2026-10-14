---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Find Similar on an account
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product compares the account with the others by meaning and lists the closest ones the User may see
  kind: product
  actor: user
  entities:
  - {entity: account, effect: reads, facts: [Name, Email]}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Find accounts similar to this one

## Trigger

The person looks for duplicates or comparable clients.

## Outcome

Up to five similar accounts the person may see are listed with their match scores.

## Edge cases

- Records are compared once the language model has processed them after they were saved.
