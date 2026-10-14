---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Log activity on a deal and picks Note
  kind: actor
  actor: user
  entities:
  - {entity: activity, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product records the Activity as Completed, linked to the Opportunity
  kind: product
  actor: user
  entities:
  - {entity: activity, effect: creates, to: Completed, facts: [Type, Title, Date and time, Duration, Outcome, Email subject, Notes, Linked records, Created by]}
  - {entity: opportunity, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Log a note on an opportunity

## Trigger

The person wants to keep a note about a deal.

## Outcome

The note is in the deal's feed, and the deal's silence clock restarts.
