---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses edit on a value, changes its name and saves
  kind: actor
  actor: admin
  entities:
  - {entity: crm-setting-value, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::administration::crm-settings'}
- text: The Product renames the CRM setting value
  kind: product
  actor: admin
  entities:
  - {entity: crm-setting-value, effect: changes, facts: [Name]}
  contexts:
    web: {place: 'web::administration::crm-settings'}
---

# Rename a value

## Trigger

A value's name is wrong or outdated.

## Outcome

Every record using it shows the new name.
