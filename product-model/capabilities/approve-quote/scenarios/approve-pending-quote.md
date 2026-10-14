---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Approve on a deal in the queue
  kind: actor
  actor: manager
  entities:
  - {entity: opportunity, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::quote-approvals'}
- text: The Product approves the Quote approval and records the Manager as reviewer
  kind: product
  actor: manager
  entities:
  - {entity: quote-approval, effect: changes, from: Pending, to: Approved, facts: [Reviewer]}
  contexts:
    web: {place: 'web::workspace::quote-approvals'}
- text: The Product emails the deal's assignee that the quote was approved
  kind: product
  actor: manager
  entities:
  - {entity: opportunity, effect: reads, facts: [Name, Assigned to]}
  contexts:
    web: {place: 'web::workspace::quote-approvals'}
---

# Approve a pending quote

## Trigger

The quote is good to send.

## Outcome

The deal shows Approved, may enter the quote stage, and its rep has an email.
