---
kind: primary
routes:
  web: Web
steps:
- text: The daily check finds an Active deal in the stage linked to Qualified
  kind: condition
  unattended: true
  entities:
  - {entity: opportunity, effect: reads, facts: [Sales stage, Stage entered on]}
- text: The deal's last client activity is at least the silent deal limit ago
  kind: condition
  entities:
  - {entity: funnel-settings, effect: reads, facts: [Silent deal limit]}
  - {entity: activity, effect: reads, facts: [Date and time]}
- text: The Product closes the Opportunity
  kind: product
  entities:
  - {entity: opportunity, effect: changes, from: Active, to: Closed, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product emails the deal's assignee that it was closed, with a link to reopen it
  kind: product
  entities:
  - {entity: opportunity, effect: reads, facts: [Name, Assigned to]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Close a silent quote-stage deal

## Trigger

The daily check runs.

## Outcome

The silent deal is Closed, its history shows why, and its owner has an email with a link to reopen it.

## Decision points

### What counts as the last client activity?

Which is the latest: the deal entering its stage, an activity logged on the deal, or an inbound synced email linked to the deal's contact or account?

- The latest is an activity logged on the deal → the clock counts from that activity.
- The latest is an inbound synced email → the clock counts from that email.
- Neither happened since the stage was entered → the clock counts from the stage entry.

## Edge cases

- Cancelled activities do not count.
- Deals that are not in the quote stage are never closed this way.
