---
entities:
- entity: contact
  shows: [First name, Last name, Email, Mobile phone, Status, Account, Assigned to, Created on]
  collects: [First name, Last name, Position, Email, Personal email, Mobile phone, Office phone, Website, Birthday, Social profiles, Contact type, Status, Description, Account, Assigned to]
entryPoints:
- web: /crm/contacts
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/contacts/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/contacts/table-components/columns.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/contacts/table-components/data-table-row-actions.tsx
---

# Contacts

The list of contacts the person may see, filtered by last name and status, with the side panels to add or update a contact.
