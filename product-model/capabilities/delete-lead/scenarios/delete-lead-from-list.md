---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete on a lead of theirs and continues
  kind: actor
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: [Company]}
  contexts:
    web: {place: 'web::workspace::leads'}
- text: The Product hides the Lead
  kind: product
  actor: user
  entities:
  - {entity: lead, effect: changes, from: Current, to: Deleted, facts: []}
  contexts:
    web: {place: 'web::workspace::leads'}
---

# Delete a lead from the list

## Trigger

A lead is a duplicate or dead.

## Outcome

The lead disappears; its history and the audit log show the deletion.
