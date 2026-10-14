---
domain: crm-settings
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/crm-settings/_actions/crm-settings.ts
---

# CRM setting value

One value of a CRM pick list other than sales stages: an industry, contact type, lead source, lead status, lead type or opportunity type.

## Information kept

- **List** — which pick list it belongs to
- **Name** — the value's name; at most 100 characters
- **Usage** — how many records use the value
