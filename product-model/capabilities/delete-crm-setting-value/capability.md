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
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/crm-settings/_components/ConfigDeleteDialog.tsx
---

# Delete a CRM setting value

Remove a pick-list value; when records use it, they are first moved to a replacement value.
