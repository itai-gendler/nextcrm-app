---
references:
- kind: code
  role: implementation
  target: prisma/schema.prisma
- kind: code
  role: implementation
  target: components/crm/activities/ActivityForm.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/activities-tasks.mdx
---

# Activity

A call, meeting, visit, note or email logged on one or more CRM records.

## Information kept

- **Type** — Call, Meeting, Visit, Note or Email
- **Title** — what the activity was; required
- **Date and time** — when it happens or happened; required
- **Duration** — minutes, for calls, meetings and visits
- **Outcome** — the result, for calls, meetings and visits
- **Email subject** — the subject, for emails
- **Notes** — free-text notes
- **Linked records** — the accounts, contacts, leads, opportunities and contracts it is about
- **Created by** — who logged it

## States

### Scheduled

Planned; calls, meetings and visits start here.

### Completed

Done; notes and emails start here.

### Cancelled

Called off.
