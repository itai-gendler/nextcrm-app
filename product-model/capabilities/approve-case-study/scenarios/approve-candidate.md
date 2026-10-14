---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Approve case study on a candidate
  kind: actor
  actor: manager
  entities:
  - {entity: case-study, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product approves the Case study
  kind: product
  actor: manager
  entities:
  - {entity: case-study, effect: changes, from: Candidate, to: Approved, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Approve a candidate

## Trigger

A manager agrees the client may be referenced.

## Outcome

The badge reads Approved; marketing may reference the account.

## Edge cases

- An account that is not a candidate cannot be approved; it must be flagged first.
