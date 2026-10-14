---
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: inngest/functions/crm/kill-rule.ts
- kind: code
  role: implementation
  target: lib/crm/client-activity.ts#getLastClientActivity
- kind: code
  role: implementation
  target: lib/crm/funnel-timers.ts#isKillDue
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Close silent opportunities

Every day, close quote-stage deals that have had no client activity for the configured number of days and tell their owners.
