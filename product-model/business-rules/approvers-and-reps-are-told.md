---
appliesTo:
- type: capability
  id: request-quote-approval
- type: capability
  id: approve-quote
- type: capability
  id: reject-quote
references:
- kind: code
  role: implementation
  target: actions/crm/opportunities/approval.ts
---

# Quote approval requests and decisions are emailed

A request emails every active manager and admin; a decision emails the deal's assignee, with the reviewer's note when there is one.
