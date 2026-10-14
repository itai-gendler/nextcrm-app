---
appliesTo:
- type: entity
  id: task-comment
  effect: creates
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: has, entity: account-task}
  - {verb: created, entity: user}
- related:
  - {verb: has, entity: account-task}
  - {verb: is assigned, entity: user}
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteCrmTask
- kind: code
  role: implementation
  target: actions/crm/tasks/add-comment.ts#addComment
---

# Only a task's creator, its assignee, a manager or an admin comments on it

A user comments on an account task they created or are assigned to; managers and admins on any account task.
