---
domain: companies
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/accounts/create-task.ts#createTask
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/accounts/[accountId]/components/NewTaskForm.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/activities-tasks.mdx
---

# Create an account task

Add a follow-up task to an account for one person; the assignee and the account's watchers are emailed.
