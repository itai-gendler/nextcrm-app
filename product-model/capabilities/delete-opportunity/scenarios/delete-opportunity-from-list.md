---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete on a deal of theirs and continues
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::opportunities'}
- text: The Product hides the Opportunity
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: changes, from: Active, to: Deleted, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunities'}
---

# Delete an opportunity from the list

## Trigger

A deal was entered by mistake.

## Outcome

The deal disappears; its history and the audit log show the deletion.

## Edge cases

- A deal marked as lost or closed is deleted the same way.
