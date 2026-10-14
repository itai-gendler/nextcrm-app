---
domain: crm-settings
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/crm-settings/_actions/crm-settings.ts
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/crm-settings/page.tsx
---

# Edit a CRM setting value

Rename a pick-list value, or change which automation a sales stage is linked to.
