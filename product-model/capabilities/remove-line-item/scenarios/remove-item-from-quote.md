---
kind: primary
routes:
  web: Web
steps:
- text: The User removes a line item
  kind: actor
  actor: user
  entities:
  - {entity: line-item, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product removes the Line item
  kind: product
  actor: user
  entities:
  - {entity: line-item, effect: removes}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product sets the Opportunity's expected revenue to the sum of the remaining line totals
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: changes, facts: [Expected revenue]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Remove an item from a quote

## Trigger

The client drops an item.

## Outcome

The item is gone and the deal's expected revenue is the sum of the remaining line totals.

## Edge cases

- Removing the last line item leaves the expected revenue as it was.
