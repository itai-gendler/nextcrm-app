---
domain: audit-log
references:
- kind: code
  role: implementation
  target: lib/audit-log.ts#writeAuditLog
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/audit-log.mdx
---

# Audit log entry

One recorded change to a CRM record: what changed, who changed it and when. Each record's History tab shows its own entries; the admin audit log shows all of them.

## Information kept

- **Record** — the kind of record and which one
- **Action** — created, updated, deleted, restored, linked or unlinked
- **Changes** — each changed field with its old and new value
- **Changed by** — the person who made the change, or System for background jobs
- **Changed on** — when the change was made
