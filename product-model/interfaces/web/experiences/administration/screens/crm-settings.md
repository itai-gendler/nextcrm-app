---
entities:
- entity: crm-setting-value
  shows: [List, Name, Usage]
  collects: [Name]
- entity: sales-stage
  shows: [Name, Automation, Usage]
  collects: [Name, Automation]
entryPoints:
- web: /admin/crm-settings
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/crm-settings/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/crm-settings/_components/ConfigList.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/crm-settings/_components/ConfigDeleteDialog.tsx
---

# CRM Settings

The pick lists used across the CRM, one tab each: industries, contact types, lead sources, lead statuses, lead types, opportunity types and sales stages, with how many records use each value.
