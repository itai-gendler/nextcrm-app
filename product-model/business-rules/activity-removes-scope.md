---
appliesTo:
- type: entity
  id: activity
  effect: removes
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: logged, entity: user}
references:
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts#assertCanWriteActivity
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/activities-tasks.mdx
---

# Only the person who logged an activity, a manager or an admin may delete it

A user may delete only the activities they logged; managers and admins any activity.

## Rationale

Changing or deleting a meeting updates or cancels the invitation sent from the organizer's Google Calendar to real attendees.
