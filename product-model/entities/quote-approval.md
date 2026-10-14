---
domain: opportunities
references:
- kind: code
  role: implementation
  target: actions/crm/opportunities/approval.ts
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# Quote approval

A manager's or admin's sign-off on a deal's quote or statement of work before it goes to the client.

## Information kept

- **Requested on** — when approval was last requested
- **Reviewer** — the manager or admin who decided
- **Note** — what the reviewer wrote, shown on a rejected quote; at most 1000 characters

## States

### Pending

Requested and waiting for a decision; the deal shows Approval pending.

### Approved

Approved; the deal may enter the quote stage.

### Rejected

Rejected with the reviewer's note; the salesperson fixes the quote and requests approval again.
