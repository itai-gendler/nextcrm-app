---
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: inngest/functions/crm/care-tasks.ts
- kind: code
  role: implementation
  target: lib/crm/funnel-timers.ts
- kind: code
  role: implementation
  target: lib/crm/auto-task.ts#createAutoTask
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Create care tasks

After a deal enters a stage linked to Care, create a check-in task, a referral-ask task and quarterly check-in tasks for its owner.
