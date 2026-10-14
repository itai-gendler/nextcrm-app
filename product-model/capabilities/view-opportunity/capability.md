---
domain: opportunities
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/get-opportunity.ts
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanReadOpportunity
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# View an opportunity

Open one Opportunity's page with its details and everything linked to it.
