---
kind: person
acts: external
relations:
- {entity: account, verb: is assigned, cardinality: one-to-many}
- {entity: account, verb: created, cardinality: one-to-many}
- {entity: account, verb: watches, cardinality: many-to-many}
- {entity: contact, verb: is assigned, cardinality: one-to-many}
- {entity: contact, verb: created, cardinality: one-to-many}
- {entity: lead, verb: is assigned, cardinality: one-to-many}
- {entity: lead, verb: created, cardinality: one-to-many}
- {entity: opportunity, verb: is assigned, cardinality: one-to-many}
- {entity: opportunity, verb: created, cardinality: one-to-many}
- {entity: activity, verb: logged, cardinality: one-to-many}
- {entity: account-task, verb: is assigned, cardinality: one-to-many}
- {entity: account-task, verb: created, cardinality: one-to-many}
references:
- kind: code
  role: implementation
  target: lib/authz/roles.ts
- kind: code
  role: implementation
  target: lib/authz/scopes/crm.ts
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# User

A salesperson. Reads, creates and changes the records that are theirs: those assigned to them or created by them, and for accounts also the ones they watch; records linked to an account of theirs they may read.
