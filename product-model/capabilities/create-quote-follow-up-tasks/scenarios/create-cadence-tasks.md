---
kind: primary
routes:
  web: Web
steps:
- text: A deal entered the stage linked to Qualified
  kind: condition
  unattended: true
  entities:
  - {entity: opportunity, effect: reads, facts: [Sales stage, Stage entered on]}
- text: On each touch's date, while the deal is still Active in that stage, the Product creates the touch's task for the deal's assignee
  kind: product
  entities:
  - {entity: funnel-settings, effect: reads, facts: [Follow-up cadence]}
  - {entity: account-task, effect: creates, facts: [Title, Description, Due date, Priority, Assigned to, Opportunity, Created on]}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product emails the assignee about the task
  kind: product
  entities:
  - {entity: account-task, effect: reads, facts: [Title, Assigned to]}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Create the quote follow-up cadence

## Trigger

A deal entered the quote stage.

## Outcome

Each touch's task is created for the deal's owner on its date, with an email to the owner.

## Edge cases

- Moving the deal to another stage cancels the touches not yet due.
- The same task is never created twice for one deal while it is open.
- A deal with no assignee gets no tasks.
