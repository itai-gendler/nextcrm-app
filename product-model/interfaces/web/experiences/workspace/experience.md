---
actors:
- user
- manager
- admin
access: authenticated
references:
- kind: code
  role: implementation
  target: lib/auth-server.ts
- kind: code
  role: implementation
  target: app/[locale]/(routes)/components/menu-items/Crm.tsx
---

# Workspace

Where active people work in the Sales section: accounts, contacts, leads and opportunities, the pipeline board, their own dashboard, record pages with activities and history, and, for managers and admins, the quote approval queue.
