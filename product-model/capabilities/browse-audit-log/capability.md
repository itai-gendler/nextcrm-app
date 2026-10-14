---
domain: audit-log
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: actions/crm/audit-log/get-audit-log-admin.ts
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/audit-log/page.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/audit-log.mdx
---

# Browse the audit log

Read every recorded change across the CRM, filtered by entity, action and date range.
