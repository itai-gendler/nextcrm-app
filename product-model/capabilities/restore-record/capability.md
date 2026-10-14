---
domain: audit-log
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: actions/crm/accounts/restore-account.ts#restoreAccount
- kind: code
  role: implementation
  target: actions/crm/opportunities/restore-opportunity.ts
- kind: code
  role: implementation
  target: components/crm/audit-log/AdminPageClient.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/audit-log.mdx
---

# Restore a deleted record

Bring back a deleted account, contact, lead or opportunity from its deletion entry in the audit log.
