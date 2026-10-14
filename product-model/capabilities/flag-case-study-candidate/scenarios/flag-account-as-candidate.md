---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Flag as candidate on the account's case study card
  kind: actor
  actor: user
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: case-study, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product records the account as a Case study candidate
  kind: product
  actor: user
  entities:
  - {entity: case-study, effect: creates, to: Candidate, facts: []}
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Flag an account as a candidate

## Trigger

A client has strong, measurable results.

## Outcome

The account's case study card shows the Candidate badge and the change is in its history.
