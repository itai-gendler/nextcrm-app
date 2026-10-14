---
domain: contacts
relations:
- {entity: opportunity, verb: is linked to, cardinality: many-to-many}
references:
- kind: code
  role: implementation
  target: prisma/schema.prisma
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#contactReadScopeWhere
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/accounts-contacts.mdx
---

# Contact

A person the team deals with, usually at one of its accounts.

## Information kept

- **First name** — the contact's first name
- **Last name** — the contact's last name; required
- **Position** — the contact's job position
- **Email** — the contact's work email, used to link synced emails and calendar meetings and for enrichment
- **Personal email** — the contact's personal email
- **Mobile phone** — the contact's mobile number
- **Office phone** — the contact's office number
- **Website** — the contact's website
- **Birthday** — the contact's birthday, optional
- **Social profiles** — the contact's Twitter, Facebook, LinkedIn, Skype, Instagram, YouTube and TikTok profiles
- **Contact type** — one of the contact types kept in CRM settings, such as Customer, Partner or Vendor
- **Status** — Active or Inactive; a new contact is Active
- **Description** — free-text notes
- **Account** — the account the contact works for
- **Assigned to** — the person responsible for the contact
- **Created on** — when the contact was added

## States

### Current

Shown in lists, on its page and wherever it is linked.

### Deleted

Hidden from every list and page; kept so an admin can restore it from the audit log.
