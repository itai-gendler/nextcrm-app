---
appliesTo:
- type: entity
  id: funnel-settings
  effect: changes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/admin/funnel-settings/_actions/funnel-settings.ts#updateFunnelSettings
---

# Only admins change the funnel settings

Funnel timing is one setting for the whole instance.
