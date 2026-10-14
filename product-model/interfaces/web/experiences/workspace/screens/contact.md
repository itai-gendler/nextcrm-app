---
entities:
- entity: contact
  shows: [First name, Last name, Position, Email, Personal email, Mobile phone, Office phone, Website, Birthday, Social profiles, Contact type, Status, Description, Account, Assigned to, Created on]
  collects: [First name, Last name, Position, Email, Personal email, Mobile phone, Office phone, Website, Birthday, Social profiles, Contact type, Status, Description, Account, Assigned to]
- entity: activity
  shows: [Type, Title, Date and time, Duration, Outcome, Email subject, Notes, Created by]
  collects: [Type, Title, Date and time, Duration, Outcome, Email subject, Notes]
- entity: audit-log-entry
  shows: [Action, Changes, Changed by, Changed on]
entryPoints:
- web: /crm/contacts/{contactId}
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/contacts/[contactId]/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/contacts/[contactId]/components/BasicView.tsx
---

# Contact

One contact: details, activities, similar contacts, the accounts and opportunities it belongs to, and its History tab.
