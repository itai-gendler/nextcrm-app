---
appliesTo:
- type: entity
  id: case-study
  effect: creates
- type: entity
  id: case-study
  effect: removes
permits:
- actors:
  - user
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: actions/crm/accounts/case-study.ts#setCaseStudyCandidate
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/accounts-contacts.mdx
---

# Salespeople, managers and admins flag and withdraw case-study candidates

Flagging an account as a candidate and withdrawing the candidacy are done from the account's case study card.
