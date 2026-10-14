---
kind: primary
routes:
  web: Web
steps:
- text: The Manager opens Approvals
  kind: actor
  actor: manager
  entities: []
  contexts:
    web: {place: 'web::workspace::quote-approvals'}
- text: The Product lists every Opportunity whose Quote approval is pending, oldest request first
  kind: product
  actor: manager
  entities:
  - {entity: opportunity, effect: reads, facts: [Name, Account, Assigned to, Budget]}
  - {entity: quote-approval, effect: reads, facts: [Requested on]}
  contexts:
    web: {place: 'web::workspace::quote-approvals'}
---

# Open the approval queue

## Trigger

A manager opens Sales → Approvals or follows the link in a request email.

## Outcome

Every pending quote is listed with its deal, account, rep, budget and request time.

## Edge cases

- People with the user role do not see Approvals and are sent away from the page.
