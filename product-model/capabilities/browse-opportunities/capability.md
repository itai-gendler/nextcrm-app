---
domain: opportunities
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/get-opportunities.ts
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#opportunityReadScopeWhere
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# Browse opportunities

List the opportunities one may see, newest first, filtered by name and by status.
