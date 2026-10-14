---
kind: primary
routes:
  web: Web
steps:
- text: The Admin sets the role of a person who holds the user role to manager
  kind: actor
  actor: admin
  entities:
  - {entity: manager, effect: reads, facts: []}
  - {entity: user, effect: reads, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product gives the person the manager role in place of the user role
  kind: product
  actor: admin
  entities:
  - {entity: user, effect: removes}
  - {entity: manager, effect: creates, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
---

# Make a user a manager

## Trigger

A salesperson becomes a sales lead.

## Outcome

The person holds the manager role and sees every CRM record.

## Edge cases

- Older instances that still store the member and viewer roles treat them as manager and user.
