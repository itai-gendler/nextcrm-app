---
domain: companies
references:
- kind: code
  role: implementation
  target: actions/crm/accounts/case-study.ts
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/accounts-contacts.mdx
---

# Case study

An account put forward as a reference client. A salesperson flags a happy client as a candidate; a manager or admin approves it, and marketing references only approved ones.

## States

### Candidate

Flagged as a case-study candidate and waiting for approval.

### Approved

Approved by a manager or admin as a reference client.
