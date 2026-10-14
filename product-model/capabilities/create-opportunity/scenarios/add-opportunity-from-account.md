---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses + on the account's Opportunities card and fills in the opportunity form
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: []}
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product creates the Opportunity linked to the Account
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: creates, to: Active, facts: [Name, Expected close date, Delivery deadline, Sales type, Sales stage, Budget, Currency, Expected revenue, Next step, Description, Account, Contact, Campaign, Assigned to, Stage entered on, Created on]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Add an opportunity from an account page

## Trigger

The person is on a company's page and opens a deal for it.

## Outcome

The deal is linked to the account and appears on its Opportunities card.
