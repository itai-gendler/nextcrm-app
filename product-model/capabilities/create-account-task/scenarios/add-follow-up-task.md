---
kind: primary
routes:
  web: Web
steps:
- text: The User fills in the task name, description, due date, priority and assignee on the account's Tasks card and chooses Create
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product creates the Account task on the account
  kind: product
  actor: user
  entities:
  - {entity: account-task, effect: creates, facts: [Title, Description, Due date, Priority, Assigned to, Created on]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product emails the assignee when it is someone else, and every other watcher of the account
  kind: product
  actor: user
  entities:
  - {entity: account-task, effect: reads, facts: [Title, Assigned to]}
  - {entity: account, effect: reads, facts: [Watchers]}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Add a follow-up task to an account

## Trigger

Someone must follow up with a company.

## Outcome

The task is on the account's Tasks card and on the assignee's My Dashboard; the assignee and the watchers have an email.
