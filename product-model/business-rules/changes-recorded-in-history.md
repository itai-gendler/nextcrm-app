---
appliesTo:
- type: capability
  id: create-account
- type: capability
  id: edit-account
- type: capability
  id: delete-account
- type: capability
  id: create-contact
- type: capability
  id: edit-contact
- type: capability
  id: delete-contact
- type: capability
  id: create-lead
- type: capability
  id: edit-lead
- type: capability
  id: delete-lead
- type: capability
  id: create-opportunity
- type: capability
  id: edit-opportunity
- type: capability
  id: delete-opportunity
- type: capability
  id: change-opportunity-sales-stage
- type: capability
  id: request-quote-approval
- type: capability
  id: approve-quote
- type: capability
  id: reject-quote
- type: capability
  id: flag-case-study-candidate
- type: capability
  id: withdraw-case-study-candidacy
- type: capability
  id: approve-case-study
- type: capability
  id: revoke-case-study-approval
- type: capability
  id: add-line-item
- type: capability
  id: edit-line-item
- type: capability
  id: remove-line-item
- type: capability
  id: restore-record
- type: capability
  id: close-silent-opportunities
- type: entity
  id: audit-log-entry
references:
- kind: code
  role: implementation
  target: lib/audit-log.ts#writeAuditLog
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/audit-log.mdx
---

# Every change to an account, contact, lead or opportunity is recorded in its history

Creating, editing, deleting and restoring these records, requesting and deciding quote approvals, and case-study changes each leave an audit log entry with who acted, when and the old and new value of each changed field. Line item changes are recorded in the audit log too.
