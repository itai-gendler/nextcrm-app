---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Log activity on an account, picks Call and enters a title, date and time, duration and notes
  kind: actor
  actor: user
  entities:
  - {entity: activity, effect: reads, facts: []}
  - {entity: account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product records the Activity, linked to the Account
  kind: product
  actor: user
  entities:
  - {entity: activity, effect: creates, to: Scheduled, facts: [Type, Title, Date and time, Duration, Outcome, Email subject, Notes, Linked records, Created by]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::account'}
---

# Log a call on an account

## Trigger

The person called someone at a company.

## Outcome

The call is first in the account's Activities feed.

## Edge cases

- Calls, meetings and visits start as Scheduled, notes and emails as Completed, unless another status is chosen.
