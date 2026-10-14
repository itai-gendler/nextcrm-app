---
appliesTo:
- type: entity
  id: case-study
  effect: changes
  to: Approved
- type: entity
  id: case-study
  effect: changes
  to: Candidate
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: actions/crm/accounts/case-study.ts#setCaseStudyApproved
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/accounts-contacts.mdx
---

# Only managers and admins approve a case study or revoke its approval

Anyone may flag an account as a candidate or withdraw it; approval and its revocation belong to managers and admins.
