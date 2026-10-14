---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the contacts list
  kind: actor
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::contacts'}
- text: The Product lists the contacts the User may see
  kind: product
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: [First name, Last name, Email, Mobile phone, Status, Account, Assigned to, Created on]}
  contexts:
    web: {place: 'web::workspace::contacts'}
- text: The User narrows the list by last name and status
  kind: actor
  actor: user
  entities:
  - {entity: contact, effect: reads, facts: [First name]}
  contexts:
    web: {place: 'web::workspace::contacts'}
---

# List one's contacts

## Trigger

The person opens Contacts in the Sales menu.

## Outcome

The person sees the contacts that are theirs or, for a user, linked to an account of theirs.

## Edge cases

- Deleted records never appear.
- View → Toggle columns shows or hides columns; Reset clears every filter.
