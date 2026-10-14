---
appliesTo:
- type: entity
  id: audit-log-entry
  effect: reads
  contexts:
  - {place: 'web::administration::audit-log'}
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: actions/crm/audit-log/get-audit-log-admin.ts
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/audit-log.mdx
---

# Only admins read the audit log across all records

Everyone else reads the history of the records they may see, on each record's History tab.
