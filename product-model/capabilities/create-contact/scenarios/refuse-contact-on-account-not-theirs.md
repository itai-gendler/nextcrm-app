---
kind: validation
routes:
  web: Web
steps:
- text: The User links the new contact to a company they may not change and sends the form
  kind: actor
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::contacts'}
- text: The Product refuses to create the Contact
  kind: product
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::contacts'}
---

# Refuse linking a new contact to an account not theirs

## Trigger

A user picks an account they may not change.

## Outcome

No contact is created; the User is told it is forbidden.
