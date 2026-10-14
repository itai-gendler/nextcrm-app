---
kind: primary
routes:
  web: Web
steps:
- text: The User edits a line item's quantity, unit price or discount and saves
  kind: actor
  actor: user
  entities:
  - {entity: line-item, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product saves the Line item with its new line total
  kind: product
  actor: user
  entities:
  - {entity: line-item, effect: changes, facts: [Quantity, Unit price, Discount type, Discount, Line total]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product sets the Opportunity's expected revenue to the sum of its line totals
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: changes, facts: [Expected revenue]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Change a line item

## Trigger

The client changes the quantity or the price is negotiated.

## Outcome

The line total and the deal's expected revenue reflect the change.
