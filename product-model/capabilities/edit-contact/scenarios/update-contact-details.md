---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Update on a contact of theirs, changes fields and saves
  kind: actor
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::contact'}
- text: The Product saves the Contact's new details
  kind: product
  actor: user
  entities:
  - {entity: contact, effect: changes, facts: [First name, Last name, Position, Email, Personal email, Mobile phone, Office phone, Website, Birthday, Social profiles, Contact type, Status, Description, Account, Assigned to]}
  contexts:
    web: {place: 'web::workspace::contact'}
---

# Update a contact's details

## Trigger

Something about the person changed.

## Outcome

The contact shows the new details and its history lists the changes.
