---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Withdraw candidacy on an approved account
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product withdraws the Case study and its approval
  kind: product
  actor: user
  entities:
  - {entity: case-study, effect: removes, from: Approved}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Withdraw an approved candidacy

## Trigger

An approved reference client should no longer be referenced.

## Outcome

The candidacy and its approval are both gone.
