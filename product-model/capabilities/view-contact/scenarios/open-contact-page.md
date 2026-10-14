---
kind: primary
routes:
  web: Web
steps:
- text: The User opens a Contact
  kind: actor
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::contact'}
- text: The Product shows the Contact's details
  kind: product
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: [First name, Last name, Position, Email, Personal email, Mobile phone, Office phone, Social profiles, Contact type, Status, Account, Assigned to]}
  contexts:
    web: {place: 'web::workspace::contact'}
---

# Open a contact page

## Trigger

The person chooses View on a Contact or follows a link to it.

## Outcome

The person sees the Contact's details and what is linked to it.
