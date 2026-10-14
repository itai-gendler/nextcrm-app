---
kind: primary
routes:
  web: Web
steps:
- text: The User types a comment and chooses Add
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::account-task'}
- text: The Product adds the Task comment to the Account task
  kind: product
  actor: user
  entities:
  - {entity: task-comment, effect: creates, facts: [Comment, Author, Posted on]}
  - {entity: account-task, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account-task'}
---

# Comment on a task

## Trigger

The person has something to say about the task.

## Outcome

The comment is in the team conversation.
