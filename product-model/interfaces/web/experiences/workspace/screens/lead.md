---
entities:
- entity: lead
  shows: [First name, Last name, Company, Job title, Email, Phone, Description, Lead source, Lead status, Lead type, Referred by, Assigned to, Created on]
  collects: [First name, Last name, Company, Job title, Email, Phone, Description, Lead source, Lead status, Lead type, Referred by, Campaign, Account, Assigned to]
- entity: activity
  shows: [Type, Title, Date and time, Duration, Outcome, Email subject, Notes, Created by]
  collects: [Type, Title, Date and time, Duration, Outcome, Email subject, Notes]
- entity: audit-log-entry
  shows: [Action, Changes, Changed by, Changed on]
entryPoints:
- web: /crm/leads/{leadId}
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/leads/[leadId]/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/leads/[leadId]/components/BasicView.tsx
---

# Lead

One lead: details, activities, similar leads and its History tab.
