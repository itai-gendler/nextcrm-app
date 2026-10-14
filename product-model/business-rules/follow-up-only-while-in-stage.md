---
appliesTo:
- type: capability
  id: create-quote-follow-up-tasks
- type: capability
  id: create-care-tasks
references:
- kind: code
  role: implementation
  target: inngest/functions/crm/qualified-cadence.ts
- kind: code
  role: implementation
  target: inngest/functions/crm/care-tasks.ts
---

# Automatic follow-up runs only while the deal stays active in the stage that started it

Each scheduled follow-up task checks the deal first: a deal that left the stage, or is no longer Active, gets no further tasks, and a stage change cancels the rest of the schedule. Timing comes from the funnel settings when the deal enters the stage.
