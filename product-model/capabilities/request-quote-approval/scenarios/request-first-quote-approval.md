---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Request approval on a deal
  kind: actor
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: [Name]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product opens a pending Quote approval for the deal
  kind: product
  actor: user
  entities:
  - {entity: quote-approval, effect: creates, to: Pending, facts: [Requested on]}
  contexts:
    web: {place: 'web::workspace::opportunity'}
- text: The Product emails every active Manager and Admin with links to the queue and the deal
  kind: product
  actor: user
  entities:
  - {entity: opportunity, effect: reads, facts: [Name]}
  - {entity: manager, effect: reads, facts: []}
  - {entity: admin, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::opportunity'}
---

# Request approval for a quote

## Trigger

The quote is ready to go to the client.

## Outcome

The deal shows Approval pending and every active manager and admin has an email linking to the approvals queue.
