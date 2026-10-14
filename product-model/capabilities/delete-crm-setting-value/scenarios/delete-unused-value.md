---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses delete on a value no record uses and confirms
  kind: actor
  actor: admin
  entities:
  - {entity: crm-setting-value, effect: reads, facts: [Name, Usage]}
  contexts:
    web: {place: 'web::administration::crm-settings'}
- text: The Product removes the CRM setting value
  kind: product
  actor: admin
  entities:
  - {entity: crm-setting-value, effect: removes}
  contexts:
    web: {place: 'web::administration::crm-settings'}
---

# Delete an unused value

## Trigger

A value nobody uses is no longer wanted.

## Outcome

The value is gone from its list.
