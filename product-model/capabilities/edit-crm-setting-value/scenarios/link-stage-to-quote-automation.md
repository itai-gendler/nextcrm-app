---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin edits a sales stage and links it to Qualified
  kind: actor
  actor: admin
  entities:
  - {entity: sales-stage, effect: reads, facts: [Name, Automation]}
  contexts:
    web: {place: 'web::administration::crm-settings'}
- text: The Product saves the Sales stage's automation
  kind: product
  actor: admin
  entities:
  - {entity: sales-stage, effect: changes, facts: [Automation]}
  contexts:
    web: {place: 'web::administration::crm-settings'}
---

# Link a sales stage to the quote automation

## Trigger

The admin marks which stage is the quote stage.

## Outcome

Deals need an approved quote to enter the stage, and entering it starts the quote follow-up cadence.
