---
appliesTo:
- type: entity
  id: line-item
  effect: removes
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: has, entity: opportunity}
  - {verb: is assigned, entity: user}
- related:
  - {verb: has, entity: opportunity}
  - {verb: created, entity: user}
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteOpportunityLineItem
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteOpportunity
---

# Only those who may change a deal remove its line items

Managers and admins remove line items on any deal; a user only on a deal assigned to them or created by them.
