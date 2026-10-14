---
domain: opportunities
relations:
- {entity: line-item, verb: has, cardinality: one-to-many}
- {entity: quote-approval, verb: has, cardinality: one-to-one}
- {entity: account-task, verb: follows up, cardinality: one-to-many}
references:
- kind: code
  role: implementation
  target: prisma/schema.prisma
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#opportunityReadScopeWhere
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Opportunity

A specific sale the team is working on, linked to an account and moved through the sales stages.

## Information kept

- **Name** — the deal's name; required
- **Expected close date** — when the deal is expected to close
- **Delivery deadline** — when delivery is due
- **Sales type** — one of the opportunity types kept in CRM settings
- **Sales stage** — the sales stage the deal is in
- **Budget** — the client's budget
- **Currency** — the deal's currency
- **Expected revenue** — the revenue expected from the deal; the sum of its line totals once it has line items
- **Next step** — what happens next
- **Description** — free-text notes
- **Account** — the account the deal is for
- **Contact** — the contact at the account
- **Campaign** — the campaign the deal came from
- **Assigned to** — the salesperson who owns the deal; the creator unless someone else is chosen
- **Stage entered on** — when the deal entered its current sales stage; follow-up timing counts from it
- **Created on** — when the deal was added

## States

### Active

Being worked; shown on the pipeline board in its stage's column.

### Inactive

Marked as lost; shown in the board's Lost column.

### Closed

Closed after going silent in the quote stage.

### Deleted

Hidden from every list and page; kept so an admin can restore it from the audit log.
