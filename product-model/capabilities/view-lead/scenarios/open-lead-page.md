---
kind: primary
routes:
  web: Web
steps:
- text: The User opens a Lead
  kind: actor
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::lead'}
- text: The Product shows the Lead's details
  kind: product
  actor: user
  entities:
  - {entity: lead, effect: reads, facts: [First name, Last name, Company, Job title, Email, Phone, Description, Lead source, Lead status, Lead type, Referred by, Assigned to]}
  contexts:
    web: {place: 'web::workspace::lead'}
---

# Open a lead page

## Trigger

The person chooses View on a Lead or follows a link to it.

## Outcome

The person sees the Lead's details and what is linked to it.
