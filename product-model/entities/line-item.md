---
domain: opportunities
references:
- kind: code
  role: implementation
  target: lib/line-items.ts#calculateLineTotal
- kind: code
  role: implementation
  target: actions/crm/opportunity-line-items/add-line-item/index.ts
---

# Line item

One product or service in a deal's quote.

## Information kept

- **Name** — what is sold; taken from the product when one is picked and no name is typed
- **Product** — the catalog product it was picked from, optional
- **Description** — free-text description
- **Quantity** — a whole number of at least 1
- **Unit price** — the price of one unit; the product's price when none is entered
- **Discount type** — Percentage or Fixed amount
- **Discount** — the discount value
- **Line total** — quantity times unit price less the discount, never below zero
- **Currency** — the deal's currency when the item was added
