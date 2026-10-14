---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager opens the contacts list
  kind: actor
  actor: manager
  entities:
  - {entity: contact, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::contacts'}
- text: The Product lists every Contact that is not deleted
  kind: product
  actor: manager
  entities:
  - {entity: contact, effect: reads, facts: [First name, Last name, Email, Mobile phone, Status, Account, Assigned to, Created on]}
  contexts:
    web: {place: 'web::workspace::contacts'}
---

# List every contact

## Trigger

A manager or admin opens the contacts list.

## Outcome

Every Contact that is not deleted is listed.
