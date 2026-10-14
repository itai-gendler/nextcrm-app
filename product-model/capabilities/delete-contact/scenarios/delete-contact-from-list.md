---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete on a contact of theirs and continues
  kind: actor
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: [Last name]}
  contexts:
    web: {place: 'web::workspace::contacts'}
- text: The Product hides the Contact
  kind: product
  actor: user
  entities:
  - {entity: contact, effect: changes, from: Current, to: Deleted, facts: []}
  contexts:
    web: {place: 'web::workspace::contacts'}
---

# Delete a contact from the list

## Trigger

A contact is a duplicate or no longer relevant.

## Outcome

The contact disappears; its history and the audit log show the deletion.
