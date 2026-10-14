---
kind: edge
routes:
  web: Web
steps:
- text: The User chooses Create on a complete task form
  kind: actor
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::account'}
- text: The Product finds no email service configured and refuses
  kind: product
  actor: user
  entities: []
  contexts:
    web: {place: 'web::workspace::account'}
---

# Refuse a task while email is not set up

## Trigger

The instance has no Resend key.

## Outcome

No task is created; the person sees that the Resend API key is not configured.

## Edge cases

- Every field is required; a missing one is refused.
