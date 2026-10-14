---
entities:
- entity: account-task
  shows: [Title, Description, Due date, Priority, Assigned to, Created on]
- entity: task-comment
  shows: [Comment, Author, Posted on]
  collects: [Comment]
entryPoints:
- web: /crm/tasks/viewtask/{taskId}
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/tasks/viewtask/[taskId]/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/tasks/viewtask/[taskId]/components/team-conversation.tsx
---

# Account task

One account task: its details, attached documents and the team conversation.
