---
entities:
- entity: funnel-settings
  shows: [Silent deal limit, Follow-up cadence, Care check-in delay, Referral ask delay, Quarterly check-in interval, Quarterly check-in count, Renewal window, Recycle delay]
  collects: [Silent deal limit, Follow-up cadence, Care check-in delay, Referral ask delay, Quarterly check-in interval, Quarterly check-in count, Renewal window, Recycle delay]
entryPoints:
- web: /admin/funnel-settings
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/funnel-settings/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/funnel-settings/_components/FunnelSettingsForm.tsx
---

# Funnel settings

The instance-wide timing of the sales funnel's automatic follow-up.
