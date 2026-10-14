---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses delete on a source that some records use, picks a replacement and chooses Reassign & Delete
  kind: actor
  actor: admin
  entities:
  - {entity: crm-setting-value, effect: reads, facts: [Name, Usage]}
  contexts:
    web: {place: 'web::administration::crm-settings'}
- text: The Product moves those Leads to the replacement source and removes the CRM setting value
  kind: product
  actor: admin
  entities:
  - {entity: lead, effect: changes, facts: [Lead source]}
  - {entity: crm-setting-value, effect: removes}
  contexts:
    web: {place: 'web::administration::crm-settings'}
---

# Reassign leads and delete a lead source

## Trigger

A lead source in use is merged into another one.

## Outcome

Every lead that used the old source now uses the replacement, and the old source is gone.

## Edge cases

- Contact types, lead statuses and lead types in use are reassigned the same way.
