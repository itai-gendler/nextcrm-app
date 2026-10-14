---
kind: validation
routes:
  web: Web
steps:
- text: The User chooses the quote stage for a deal and saves
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The new Sales stage is linked to Qualified and the deal's Quote approval is not Approved
  kind: condition
  entities:
  - {entity: sales-stage, effect: reads, facts: [Automation]}
  - {entity: quote-approval, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product refuses the change
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Refuse the quote stage without an approved quote

## Trigger

The person moves a deal into the stage linked to Qualified while its quote is not approved.

## Outcome

Nothing is saved; the person is told quote approval is required and to request it from the deal page.
