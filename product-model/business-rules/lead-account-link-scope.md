---
appliesTo:
- type: entity
  id: lead
  effect: creates
permits:
- actors:
  - manager
  - admin
- actors:
  - user
  when:
  - {fact: Account, absent: true}
- related:
  - {verb: has, entity: account}
  - {verb: is assigned, entity: user}
- related:
  - {verb: has, entity: account}
  - {verb: created, entity: user}
- related:
  - {verb: has, entity: account}
  - {verb: watches, entity: user}
references:
- kind: code
  role: implementation
  target: actions/crm/leads/create-lead.ts#createLead
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteAccount
---

# A new lead is linked only to an account its creator may change

Creating a lead without an account is open to everyone. Linking the new lead to an account needs the right to change that account: managers and admins may link any account, a user only one they are assigned to, created or watch.
