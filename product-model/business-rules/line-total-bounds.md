---
appliesTo:
- type: capability
  id: add-line-item
- type: capability
  id: edit-line-item
references:
- kind: code
  role: implementation
  target: lib/line-items.ts#calculateLineTotal
---

# A line total is quantity times unit price less the discount, never below zero

A percentage discount is at most 100%; a fixed discount is subtracted from the line's amount; the result is rounded to cents and never negative.
