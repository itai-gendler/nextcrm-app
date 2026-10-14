---
domain: companies
relations:
- {entity: contact, verb: has, cardinality: one-to-many}
- {entity: lead, verb: has, cardinality: one-to-many}
- {entity: opportunity, verb: has, cardinality: one-to-many}
- {entity: account-task, verb: has, cardinality: one-to-many}
- {entity: case-study, verb: has, cardinality: one-to-one}
references:
- kind: code
  role: implementation
  target: prisma/schema.prisma
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#accountReadScopeWhere
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/accounts-contacts.mdx
---

# Account

A company the team sells to. The Sales menu calls accounts Companies; pages and forms call them accounts.

## Information kept

- **Name** — the company's name; required
- **Office phone** — the company's main phone number
- **Email** — the company's email address, also used to link synced emails
- **Website** — the company's website
- **Account ID** — the company's registration number
- **VAT number** — the company's VAT number
- **Billing address** — street, postal code, city, state and country for billing
- **Shipping address** — street, postal code, city, state and country for shipping
- **Annual revenue** — the company's annual revenue as entered
- **Parent company** — the company this one is a member of
- **Industry** — one of the industries kept in CRM settings
- **Description** — free-text notes about the company
- **Status** — Active or Inactive; a new account is Active
- **Assigned to** — the person responsible for the account; the creator unless someone else is chosen
- **Watchers** — the people who follow the account
- **Created on** — when the account was added

## States

### Current

Shown in lists, on its page and wherever it is linked.

### Deleted

Hidden from every list and page; kept so an admin can restore it from the audit log.
