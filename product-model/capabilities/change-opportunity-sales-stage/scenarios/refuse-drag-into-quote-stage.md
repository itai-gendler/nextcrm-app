---
kind: validation
routes:
  web: Web
steps:
- text: The User drags a deal into the quote stage's column
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::pipeline'}
- text: The target Sales stage is linked to Qualified and the deal's Quote approval is not Approved
  kind: condition
  entities:
  - {entity: sales-stage, effect: reads, facts: [Automation]}
  - {entity: quote-approval, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::pipeline'}
- text: The Product refuses the move
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::pipeline'}
---

# Refuse dragging into the quote stage without approval

## Trigger

The person drags a deal whose quote is not approved into the stage linked to Qualified.

## Outcome

The card stays where it was and the person is told quote approval is required.
