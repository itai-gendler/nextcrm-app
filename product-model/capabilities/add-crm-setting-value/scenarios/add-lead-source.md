---
kind: primary
routes:
  web: Web
steps:
- text: The Admin opens the sources tab, chooses to add a value, enters a name and saves
  kind: actor
  actor: admin
  entities: []
  contexts:
    web: {place: 'web::administration::crm-settings'}
- text: The Product adds the CRM setting value to that list
  kind: product
  actor: admin
  entities:
  - {entity: crm-setting-value, effect: creates, facts: [List, Name, Usage]}
  contexts:
    web: {place: 'web::administration::crm-settings'}
---

# Add a lead source

## Trigger

The team gets leads from a new channel.

## Outcome

The new source can be picked on leads.

## Edge cases

- A name is required and at most 100 characters long.
