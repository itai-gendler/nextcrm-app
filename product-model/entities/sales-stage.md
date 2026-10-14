---
domain: crm-settings
references:
- kind: code
  role: implementation
  target: prisma/schema.prisma
- kind: code
  role: implementation
  target: lib/crm/stage-kinds.ts
---

# Sales stage

One stage of the sales pipeline, a column on the pipeline board.

## Information kept

- **Name** — the stage's name; at most 100 characters
- **Automation** — the funnel automation the stage is linked to: Pre-sale, Qualified (the quote stage), Purchase order, Delivery, Care, or none
- **Probability** — the stage's win probability
- **Order** — the stage's position on the board
- **Usage** — how many opportunities are in the stage
