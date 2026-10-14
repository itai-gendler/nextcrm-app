---
domain: companies
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/accounts/update-account.ts#updateAccount
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteAccount
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Edit an account

Change an account's details from its page or its row in the list.
