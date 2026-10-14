---
kind: primary
routes:
  web: Web
steps:
- text: The User opens an Opportunity
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product shows the Opportunity's details
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: [Name, Expected close date, Sales type, Sales stage, Budget, Currency, Next step, Description, Account, Assigned to]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Open an opportunity page

## Trigger

The person chooses View on a Opportunity or follows a link to it.

## Outcome

The person sees the Opportunity's details and what is linked to it.
