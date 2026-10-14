---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the opportunities list
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunities'}
- text: The Product lists the opportunities the User may see
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: [Name, Account, Assigned to, Budget, Expected close date, Next step]}
  contexts:
    web: {place: 'web::workspace::opportunities'}
- text: The User narrows the list by name and status
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::opportunities'}
---

# List one's opportunities

## Trigger

The person opens Opportunities in the Sales menu.

## Outcome

The person sees the opportunities that are theirs or, for a user, linked to an account of theirs.

## Edge cases

- Deleted records never appear.
- View → Toggle columns shows or hides columns; Reset clears every filter.
