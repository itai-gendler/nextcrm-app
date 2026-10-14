---
kind: primary
routes:
  web: Web
steps:
- text: The User opens an Account
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product shows the Account's details
  kind: product
  actor: user
  entities:
  - {entity: account, effect: reads, facts: [Name, Office phone, Email, Website, Account ID, VAT number, Billing address, Shipping address, Annual revenue, Parent company, Industry, Description, Status, Assigned to]}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Open an account page

## Trigger

The person chooses View on a Account or follows a link to it.

## Outcome

The person sees the Account's details and what is linked to it.
