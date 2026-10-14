---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses + on the account's Contacts card and fills in the contact form
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  - {entity: contact, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product creates the Contact linked to the Account
  kind: product
  actor: user
  entities:
  - {entity: contact, effect: creates, to: Current, facts: [First name, Last name, Position, Email, Personal email, Mobile phone, Office phone, Website, Birthday, Social profiles, Contact type, Status, Description, Account, Assigned to, Created on]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Add a contact from an account page

## Trigger

The person is on a company's page and adds someone who works there.

## Outcome

The contact is linked to the account and appears on its Contacts card.
