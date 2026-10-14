---
kind: alternative
routes:
  web: Web
steps:
- text: The User reads the reviewer's note on the Rejected badge, fixes the quote and chooses Request approval
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product makes the Quote approval pending again and clears its note
  kind: product
  actor: user
  entities:
  - {entity: quote-approval, effect: changes, from: Rejected, to: Pending, facts: [Requested on, Note]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Request approval again after a rejection

## Trigger

The person fixed a rejected quote.

## Outcome

The deal is pending approval again and the old note is cleared.
