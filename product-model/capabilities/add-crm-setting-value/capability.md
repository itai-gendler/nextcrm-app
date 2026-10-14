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

# Add a CRM setting value

Add a value to one of the CRM pick lists: an industry, contact type, lead source, lead status, lead type, opportunity type or sales stage.
