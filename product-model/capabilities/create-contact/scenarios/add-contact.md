---
kind: primary
routes:
  web: Web
steps:
- text: The User fills in the contact form with at least a last name and chooses Create contact
  kind: actor
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::contacts'}
- text: The Product creates the Contact
  kind: product
  actor: user
  entities:
  - {entity: contact, effect: creates, to: Current, facts: [First name, Last name, Position, Email, Personal email, Mobile phone, Office phone, Website, Birthday, Social profiles, Contact type, Status, Description, Account, Assigned to, Created on]}
  contexts:
    web: {place: 'web::workspace::contacts'}
- text: The Product emails the assignee when it is someone else
  kind: product
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: [First name, Last name, Assigned to]}
  contexts:
    web: {place: 'web::workspace::contacts'}
---

# Add a contact

## Trigger

The person meets someone new.

## Outcome

The contact exists, Active, and its assignee has an email when it is someone else.
