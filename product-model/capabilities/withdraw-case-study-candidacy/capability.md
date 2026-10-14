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

# Withdraw a case-study candidacy

Take an account's case-study candidacy back, which also takes back any approval.
