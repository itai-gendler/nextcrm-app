---
kind: edge
routes:
  web: Web
steps:
- text: The User enters a valid code
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The User account is Inactive
  kind: condition
  entities:
  - {entity: user-account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product shows the inactive page instead of the workspace
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
---

# Turn away an inactive person

## Trigger

A person an admin deactivated signs in.

## Outcome

The person sees the inactive page and cannot use the CRM.
