---
domain: companies
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/account/get-task.ts
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/tasks/viewtask/[taskId]/page.tsx
---

# View an account task

Open an account task's page with its details and team conversation.
