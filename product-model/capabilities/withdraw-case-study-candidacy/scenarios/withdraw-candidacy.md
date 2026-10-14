---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Withdraw candidacy
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product withdraws the Case study
  kind: product
  actor: user
  entities:
  - {entity: case-study, effect: removes, from: Candidate}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Withdraw a candidacy

## Trigger

The client is no longer a good reference.

## Outcome

The account is no longer a case-study candidate.
