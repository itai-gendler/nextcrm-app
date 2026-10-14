---
id: nextcrm
summary: 'Open-source, self-hosted CRM: accounts, contacts, leads and opportunities moved through sales stages, with activities, follow-up tasks, quote approval and a full change history.'
category: crm
tags:
- crm
- sales-pipeline
- self-hosted
authors:
- name: Pavel Dovhomilja
  url: https://github.com/pdovhomilja/nextcrm-app
license: MIT
languages:
- en
- cs
- de
- uk
limitations:
- People sign in with a one-time code sent to their email address or with a Google account; there are no passwords.
- A new person who signs up waits for an admin to activate them before they can use the CRM.
- 'There are three fixed roles, user, manager and admin: users work with the records that are theirs, managers and admins with every record.'
- Deleting an account, contact, lead or opportunity only hides it; an admin can restore it from the audit log.
- Follow-up timing for the sales funnel is one setting for the whole instance, not per team or per user.
references:
- kind: doc
  role: context
  target: README.md
- kind: doc
  role: context
  target: apps/docs/content/docs/index.mdx
- kind: doc
  role: intent
  target: apps/docs/content/docs/users/crm/records.mdx
---

# NextCRM

NextCRM is a CRM a sales team runs on its own server. Salespeople keep the companies they sell to (accounts, shown as Companies), the people at those companies (contacts), potential buyers not yet qualified (leads), and the deals they are working (opportunities). Deals move through sales stages on a pipeline board; a manager or admin signs off a deal's quote before it may enter the quote stage, and stages linked to automation create follow-up tasks on a schedule and close quote-stage deals that have gone silent. Every record page carries a feed of calls, meetings, visits, notes and emails, a list of similar records, and a history of every change. Users see and change their own records; managers and admins see and change all of them; admins also manage people, the CRM's pick lists and funnel timing, and restore deleted records from the audit log.

## Intent

NextCRM is an open-source CRM built on Next.js, Prisma and PostgreSQL that you can run yourself with Docker. Beside the usual CRM modules it aims to give a team one place for its customer work, with a change trail on every record and a sales funnel that keeps deals moving.
