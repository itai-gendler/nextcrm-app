---
kind: primary
routes:
  web: Web
steps:
- text: The User opens an Account task
  kind: actor
  actor: user
  entities:
  - {entity: account-task, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account-task'}
- text: The Product shows the Account task and its Task comments
  kind: product
  actor: user
  entities:
  - {entity: account-task, effect: reads, facts: [Title, Description, Due date, Priority, Assigned to, Created on]}
  - {entity: task-comment, effect: reads, facts: [Comment, Author, Posted on]}
  contexts:
    web: {place: 'web::workspace::account-task'}
---

# Open a task's page

## Trigger

The person chooses View on a task.

## Outcome

The person sees the task and its conversation.
