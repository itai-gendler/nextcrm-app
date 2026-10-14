---
domain: companies
availability:
- {place: 'web::workspace'}
references:
- kind: code
  role: implementation
  target: actions/crm/accounts/case-study.ts
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/accounts/[accountId]/components/CaseStudyCard.tsx
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/accounts-contacts.mdx
---

# Flag a case-study candidate

Suggest an account as a reference client.
