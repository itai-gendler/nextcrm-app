---
kind: validation
routes:
  web: Web
steps:
- text: The Admin sends an invitation to an address an existing User account uses
  kind: actor
  actor: admin
  entities:
  - {entity: user-account, effect: reads, facts: []}
  contexts:
    web: {place: 'web::administration::users'}
- text: The Product refuses the invitation
  kind: product
  actor: admin
  entities:
  - {entity: user-account, effect: reads, facts: [Email]}
  contexts:
    web: {place: 'web::administration::users'}
---

# Refuse an invitation for a known email

## Trigger

The address already belongs to someone.

## Outcome

Nothing is created; the admin sees that the user already exists.

## Edge cases

- The invitation is refused with an error when no Resend key is configured.
- Name, email and language are all required.
