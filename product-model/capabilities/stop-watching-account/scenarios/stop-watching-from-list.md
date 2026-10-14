---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Stop watching Account
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: [Watchers]}
  contexts:
    web: {place: 'web::workspace::accounts'}
- text: The Product removes the User from the Account's watchers
  kind: product
  actor: user
  entities:
  - {entity: account, effect: changes, facts: [Watchers]}
  contexts:
    web: {place: 'web::workspace::accounts'}
---

# Stop watching from the list

## Trigger

The person no longer wants to follow a company.

## Outcome

The person is no longer a watcher.

## Edge cases

- A user who watches an account only because of watching it loses access to it when they stop.
