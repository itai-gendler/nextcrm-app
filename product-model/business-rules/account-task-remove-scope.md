---
appliesTo:
- type: entity
  id: account-task
  effect: removes
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: created, entity: user}
- related:
  - {verb: is assigned, entity: user}
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteCrmTask
- kind: code
  role: implementation
  target: actions/crm/tasks/delete-task.ts#deleteTask
---

# Only a task's creator, its assignee, a manager or an admin deletes it

A user deletes an account task they created or are assigned to; managers and admins any account task.
