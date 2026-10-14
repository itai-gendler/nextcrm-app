---
appliesTo:
- type: entity
  id: account-task
  effect: creates
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: has, entity: account}
  - {verb: is assigned, entity: user}
- related:
  - {verb: has, entity: account}
  - {verb: created, entity: user}
- related:
  - {verb: has, entity: account}
  - {verb: watches, entity: user}
- unattended: true
references:
- kind: code
  role: implementation
  target: actions/crm/accounts/create-task.ts#createTask
- kind: code
  role: implementation
  target: lib/crm/auto-task.ts#createAutoTask
---

# A task is added to an account only by someone who may change that account

Managers and admins add tasks to any account; a user only to an account they are assigned to, created or watch. The Product's own funnel automation creates follow-up tasks for a deal's owner.
