---
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/funnel-settings/_actions/funnel-settings.ts#updateFunnelSettings
- kind: code
  role: implementation
  target: lib/crm/funnel-timers.ts
---

# Change funnel settings

Set the instance-wide timing of the funnel's follow-up tasks and of closing silent deals.
