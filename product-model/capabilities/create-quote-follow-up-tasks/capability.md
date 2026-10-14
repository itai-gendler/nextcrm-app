---
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: inngest/functions/crm/qualified-cadence.ts
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

# Create quote follow-up tasks

After a deal enters the stage linked to Qualified, create five follow-up tasks for its owner on the funnel cadence.
