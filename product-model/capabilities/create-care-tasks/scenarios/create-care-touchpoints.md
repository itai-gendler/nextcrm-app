---
kind: primary
routes:
  web: Web
steps:
- text: A deal entered a stage linked to Care
  kind: condition
  unattended: true
  entities:
  - {entity: opportunity, effect: reads, facts: [Sales stage, Stage entered on]}
- text: On each touchpoint's date, while the deal is still Active in that stage, the Product creates the touchpoint's task for the deal's assignee
  kind: product
  entities:
  - {entity: funnel-settings, effect: reads, facts: [Care check-in delay, Referral ask delay, Quarterly check-in interval, Quarterly check-in count]}
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

# Create the care touchpoints

## Trigger

A delivered deal entered a care stage.

## Outcome

The owner gets each care task on its date, with an email.

## Edge cases

- Moving the deal to another stage cancels the touchpoints not yet due.
