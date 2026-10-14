---
domain: companies
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/get-account.ts
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanReadAccount
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/accounts-contacts.mdx
---

# View an account

Open one Account's page with its details and everything linked to it.
