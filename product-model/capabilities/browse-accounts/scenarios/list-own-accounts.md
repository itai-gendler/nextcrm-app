---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the accounts list
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::accounts'}
- text: The Product lists the accounts the User may see
  kind: product
  actor: user
  entities:
  - {entity: account, effect: reads, facts: [Name, Email, Status, Assigned to, Created on]}
  contexts:
    web: {place: 'web::workspace::accounts'}
- text: The User narrows the list by name and status
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::accounts'}
---

# List one's accounts

## Trigger

The person opens Companies in the Sales menu.

## Outcome

The person sees the accounts assigned to them, created by them or watched by them.

## Edge cases

- Deleted records never appear.
- View → Toggle columns shows or hides columns; Reset clears every filter.
