---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Revoke approval
  kind: actor
  actor: manager
  entities: []
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product returns the Case study to Candidate
  kind: product
  actor: manager
  entities:
  - {entity: case-study, effect: changes, from: Approved, to: Candidate, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Revoke an approval

## Trigger

A manager no longer wants the client referenced.

## Outcome

The account is a candidate again.
