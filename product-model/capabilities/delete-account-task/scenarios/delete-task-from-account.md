---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete on a task in the account's Tasks card
  kind: actor
  actor: user
  entities:
  - {entity: account-task, effect: reads, facts: [Title]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product removes the Account task and its comments
  kind: product
  actor: user
  entities:
  - {entity: account-task, effect: removes}
  - {entity: task-comment, effect: removes, with: account-task}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Delete a task from an account

## Trigger

A task is no longer needed.

## Outcome

The task and its comments are gone.
