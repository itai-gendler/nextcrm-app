---
appliesTo:
- type: entity
  id: account
  effect: changes
  from: Deleted
- type: entity
  id: contact
  effect: changes
  from: Deleted
- type: entity
  id: lead
  effect: changes
  from: Deleted
- type: entity
  id: opportunity
  effect: changes
  from: Deleted
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: actions/crm/accounts/restore-account.ts#restoreAccount
- kind: code
  role: implementation
  target: actions/crm/opportunities/restore-opportunity.ts
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/audit-log.mdx
---

# Only admins restore deleted records

Deleted accounts, contacts, leads and opportunities come back only from the admin audit log.
