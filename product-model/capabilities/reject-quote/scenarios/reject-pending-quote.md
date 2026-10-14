---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Reject, writes what must change and chooses Reject quote
  kind: actor
  actor: manager
  entities: []
  contexts:
    web: {place: 'web::workspace::quote-approvals'}
- text: The Product rejects the Quote approval with the note and records the Manager as reviewer
  kind: product
  actor: manager
  entities:
  - {entity: quote-approval, effect: changes, from: Pending, to: Rejected, facts: [Reviewer, Note]}
  contexts:
    web: {place: 'web::workspace::quote-approvals'}
- text: The Product emails the deal's assignee the rejection and the note
  kind: product
  actor: manager
  entities:
  - {entity: opportunity, effect: reads, facts: [Name, Assigned to]}
  - {entity: quote-approval, effect: reads, facts: [Note]}
  contexts:
    web: {place: 'web::workspace::quote-approvals'}
---

# Reject a pending quote with a note

## Trigger

The quote needs changes.

## Outcome

The deal shows Rejected with the note on hover, and its rep has the note by email.

## Edge cases

- A note longer than 1000 characters is cut to 1000.
