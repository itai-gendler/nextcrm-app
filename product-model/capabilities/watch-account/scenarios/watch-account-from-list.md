---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Watch Account on an account they may change
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::accounts'}
- text: The Product adds the User to the Account's watchers
  kind: product
  actor: user
  entities:
  - {entity: account, effect: changes, facts: [Watchers]}
  contexts:
    web: {place: 'web::workspace::accounts'}
---

# Watch an account from the list

## Trigger

The person wants to follow a company.

## Outcome

The person is one of the account's watchers.
