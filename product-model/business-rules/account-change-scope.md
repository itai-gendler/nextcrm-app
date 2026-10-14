---
appliesTo:
- type: entity
  id: account
  effect: changes
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: is assigned, entity: user}
- related:
  - {verb: created, entity: user}
- related:
  - {verb: watches, entity: user}
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteAccount
- kind: code
  role: implementation
  target: actions/crm/accounts/watch-account.ts#watchAccount
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Users change only the accounts assigned to them, created by them or watched by them

Managers and admins change and delete any account. A user changes, deletes, watches and stops watching only an account they are assigned to, created or watch, so watching never widens what a user may change.
