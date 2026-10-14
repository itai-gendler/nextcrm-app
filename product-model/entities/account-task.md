---
domain: companies
relations:
- {entity: task-comment, verb: has, cardinality: one-to-many}
references:
- kind: code
  role: implementation
  target: prisma/schema.prisma
- kind: code
  role: implementation
  target: actions/crm/accounts/create-task.ts
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/activities-tasks.mdx
---

# Account task

A follow-up task attached to an account, assigned to one person, separate from project tasks.

## Information kept

- **Title** — the task's name; required
- **Description** — what to do; required
- **Due date** — when it is due
- **Priority** — the task's priority; required
- **Assigned to** — the person who must do it; required
- **Opportunity** — the deal an automatic follow-up task belongs to
- **Created on** — when the task was created
