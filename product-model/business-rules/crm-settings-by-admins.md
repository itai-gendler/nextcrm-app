---
appliesTo:
- type: entity
  id: crm-setting-value
  effect: creates
- type: entity
  id: crm-setting-value
  effect: changes
- type: entity
  id: crm-setting-value
  effect: removes
- type: entity
  id: sales-stage
  effect: creates
- type: entity
  id: sales-stage
  effect: changes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/crm-settings/_actions/crm-settings.ts
---

# Only admins change the CRM pick lists and sales stages

Adding, renaming, relinking and deleting industries, contact types, lead sources, lead statuses, lead types, opportunity types and sales stages is reserved to admins.
