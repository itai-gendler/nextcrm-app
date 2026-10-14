---
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/activities/update-activity.ts#updateActivity
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteActivity
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/activities-tasks.mdx
---

# Edit an activity

Change an activity's details or status.
