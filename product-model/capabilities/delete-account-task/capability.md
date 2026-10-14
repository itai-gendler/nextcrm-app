---
domain: companies
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/tasks/delete-task.ts#deleteTask
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteCrmTask
---

# Delete an account task

Remove an account task with its conversation.
