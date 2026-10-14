---
domain: users
relations:
- {entity: user, verb: holds, cardinality: one-to-one}
- {entity: manager, verb: holds, cardinality: one-to-one}
- {entity: admin, verb: holds, cardinality: one-to-one}
references:
- kind: code
  role: implementation
  target: prisma/schema.prisma
- kind: code
  role: implementation
  target: lib/auth.ts
- kind: doc
  role: intent
  target: apps/docs/content/docs/admins/users-and-roles.mdx
---

# User account

A person's account in NextCRM: who they are, how they sign in and whether they may use the CRM, whatever role they hold.

## Information kept

- **Name** — the person's name
- **Email** — the address they sign in with; unique
- **Language** — the language of their emails and interface: English, Czech, German or Ukrainian
- **Last login** — when they last signed in

## States

### Pending

Signed up and waiting for an admin; sees a waiting page after signing in.

### Active

May use the CRM.

### Inactive

Deactivated by an admin; sees an inactive page after signing in.
