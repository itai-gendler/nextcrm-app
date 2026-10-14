---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager opens the leads list
  kind: actor
  actor: manager
  entities:
  - {entity: lead, effect: reads, facts: []}
  contexts:
    web: {place: 'web::workspace::leads'}
- text: The Product lists every Lead that is not deleted
  kind: product
  actor: manager
  entities:
  - {entity: lead, effect: reads, facts: [First name, Last name, Company, Email, Phone, Lead status, Assigned to, Created on]}
  contexts:
    web: {place: 'web::workspace::leads'}
---

# List every lead

## Trigger

A manager or admin opens the leads list.

## Outcome

Every Lead that is not deleted is listed.
