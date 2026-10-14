---
domain: leads
references:
- kind: code
  role: implementation
  target: prisma/schema.prisma
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#leadReadScopeWhere
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Lead

A person or company that might buy, not yet a deal.

## Information kept

- **First name** — the lead's first name
- **Last name** — the lead's last name; required
- **Company** — the company name as given
- **Job title** — the lead's job title
- **Email** — the lead's email address
- **Phone** — the lead's phone number
- **Description** — free-text notes
- **Lead source** — one of the lead sources kept in CRM settings
- **Lead status** — one of the lead statuses kept in CRM settings, such as New, In progress or Completed
- **Lead type** — one of the lead types kept in CRM settings
- **Referred by** — who referred the lead
- **Campaign** — the campaign the lead came from
- **Account** — an existing account the lead is linked to
- **Assigned to** — the person responsible for the lead; the creator unless someone else is chosen
- **Created on** — when the lead was added

## States

### Current

Shown in lists, on its page and wherever it is linked.

### Deleted

Hidden from every list and page; kept so an admin can restore it from the audit log.
