---
entities:
- entity: audit-log-entry
  shows: [Record, Action, Changes, Changed by, Changed on]
entryPoints:
- web: /admin/audit-log
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/audit-log/page.tsx
- kind: code
  role: implementation
  target: components/crm/audit-log/AdminPageClient.tsx
- kind: code
  role: implementation
  target: components/crm/audit-log/AdminFilters.tsx
---

# Audit Log

Every recorded change across the CRM, filterable by entity, action and date range, with a restore button on deletions.
