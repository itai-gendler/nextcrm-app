---
kind: primary
routes:
  web: Web
steps:
- text: The User opens My Dashboard
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::my-dashboard'}
- text: The Product shows the User's open Account tasks, the Leads assigned to them and their active Opportunities
  kind: product
  actor: user
  entities:
  - {entity: account-task, effect: reads, facts: [Title, Due date, Priority]}
  - {entity: lead, effect: reads, facts: [First name, Last name, Company, Lead status]}
  - {entity: opportunity, effect: reads, facts: [Name, Sales stage, Budget, Expected close date]}
  contexts:
    web: {place: 'web::workspace::my-dashboard'}
---

# Open My Dashboard

## Trigger

The person opens Sales → My Dashboard.

## Outcome

The person sees their open tasks, their leads and their active deals.
