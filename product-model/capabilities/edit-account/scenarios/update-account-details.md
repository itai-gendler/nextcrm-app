---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Update on an account of theirs, changes fields and saves
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product saves the Account's new details
  kind: product
  actor: user
  entities:
  - {entity: account, effect: changes, facts: [Name, Office phone, Email, Website, Account ID, VAT number, Billing address, Shipping address, Annual revenue, Parent company, Industry, Description, Assigned to]}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Update an account's details

## Trigger

Something about the company changed.

## Outcome

The account shows the new details and its history lists each changed field with its old and new value.
