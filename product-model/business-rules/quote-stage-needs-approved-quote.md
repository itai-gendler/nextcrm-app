---
appliesTo:
- type: capability
  id: edit-opportunity
- type: capability
  id: change-opportunity-sales-stage
references:
- kind: code
  role: implementation
  target: lib/crm/approval-gate.ts#qualifiedEntryBlockReason
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/leads-opportunities.mdx
---

# A deal enters the quote stage only with an approved quote

When a sales stage is linked to Qualified, moving a deal into it, by editing the deal or dragging its card, is refused until the deal's quote approval is Approved. Moves to other stages, staying in place and clearing the stage are not affected.
