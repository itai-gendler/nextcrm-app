---
kind: primary
routes:
  web: Web
steps:
- text: The User opens Add Line Item, picks a product, sets the quantity and discount and saves
  kind: actor
  actor: user
  entities:
  - {entity: line-item, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product adds the Line item, taking the product's price when no price was entered, and works out its line total
  kind: product
  actor: user
  entities:
  - {entity: line-item, effect: creates, facts: [Name, Product, Description, Quantity, Unit price, Discount type, Discount, Line total, Currency]}
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

# Add a product to a quote

## Trigger

The client will buy something from the catalog.

## Outcome

The line item is in the table with its line total, and the deal's expected revenue is the new subtotal.

## Edge cases

- A custom item without a product needs a typed name.
- A fixed discount larger than the line's amount makes the line total zero.
