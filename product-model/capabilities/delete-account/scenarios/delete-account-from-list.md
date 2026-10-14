---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete on an account of theirs and continues past the warning that it is only hidden
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::accounts'}
- text: The Product hides the Account
  kind: product
  actor: user
  entities:
  - {entity: account, effect: changes, from: Current, to: Deleted, facts: []}
  contexts:
    web: {place: 'web::workspace::accounts'}
---

# Delete an account from the list

## Trigger

An account is a duplicate or no longer relevant.

## Outcome

The account disappears from lists and pages; its history and the audit log show the deletion.
