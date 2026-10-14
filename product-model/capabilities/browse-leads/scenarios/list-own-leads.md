---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the leads list
  kind: actor
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::leads'}
- text: The Product lists the leads the User may see
  kind: product
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: [First name, Last name, Company, Email, Phone, Lead status, Assigned to, Created on]}
  contexts:
    web: {place: 'web::workspace::leads'}
- text: The User narrows the list by company and status
  kind: actor
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: [First name]}
  contexts:
    web: {place: 'web::workspace::leads'}
---

# List one's leads

## Trigger

The person opens Leads in the Sales menu.

## Outcome

The person sees the leads that are theirs or, for a user, linked to an account of theirs.

## Edge cases

- Deleted records never appear.
- View → Toggle columns shows or hides columns; Reset clears every filter.
