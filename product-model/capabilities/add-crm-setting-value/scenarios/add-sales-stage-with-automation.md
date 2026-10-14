---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin opens the Sales Stages tab, adds a stage and links it to an automation
  kind: actor
  actor: admin
  entities:
  - {entity: sales-stage, effect: reads, facts: []}
  contexts:
    web: {place: 'web::administration::crm-settings'}
- text: The Product adds the Sales stage
  kind: product
  actor: admin
  entities:
  - {entity: sales-stage, effect: creates, facts: [Name, Automation, Usage]}
  contexts:
    web: {place: 'web::administration::crm-settings'}
---

# Add a sales stage linked to automation

## Trigger

The pipeline gets a new stage that should start follow-up.

## Outcome

The stage is a new column on the board and entering it triggers its automation.
