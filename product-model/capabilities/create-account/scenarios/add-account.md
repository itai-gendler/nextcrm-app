---
kind: primary
routes:
  web: Web
steps:
- text: The User fills in the account form with at least a name and chooses Create account
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::accounts'}
- text: The Product creates the Account, Active and assigned to the chosen person or to the User
  kind: product
  actor: user
  entities:
  - {entity: account, effect: creates, to: Current, facts: [Name, Office phone, Email, Website, Account ID, VAT number, Billing address, Shipping address, Annual revenue, Parent company, Industry, Description, Assigned to, Status, Created on]}
  contexts:
    web: {place: 'web::workspace::accounts'}
---

# Add an account

## Trigger

The person starts working with a new company.

## Outcome

The account is Active, assigned to the chosen person or to its creator, and recorded in its history.

## Edge cases

- With a company registry plugin installed, Load from registry fills the form from the registration number and country.
