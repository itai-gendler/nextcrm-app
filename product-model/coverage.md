---
scope: 'The CRM core of the web app: sign-in, users and roles, accounts, contacts, leads, opportunities with line items and quote approval, the pipeline board, activities, account tasks, history and audit log, CRM and funnel settings, and the funnel automation jobs.'
method: Static inspection of server actions, authorization scopes, pages, background jobs and the Prisma schema, with the user and admin documentation as a lead.
covered:
- description: Sign-in, session and status gate code.
  paths:
  - lib/auth.ts
  - lib/auth-server.ts
  - lib/auth-client.ts
  - proxy.ts
  - app/[locale]/(auth)/
- description: Role and record-scope authorization code.
  paths:
  - lib/authz/
- description: Account, case-study, watcher and account task actions.
  paths:
  - actions/crm/accounts/
  - actions/crm/account/
  - actions/crm/tasks/
- description: Contact, lead and opportunity actions, line items and quote approval.
  paths:
  - actions/crm/contacts/
  - actions/crm/leads/
  - actions/crm/opportunities/
  - actions/crm/opportunity/
  - actions/crm/opportunity-line-items/
  - lib/line-items.ts
- description: CRM record read queries.
  paths:
  - actions/crm/get-account.ts
  - actions/crm/get-accounts.ts
  - actions/crm/get-contact.ts
  - actions/crm/get-contacts.ts
  - actions/crm/get-lead.ts
  - actions/crm/get-leads.ts
  - actions/crm/get-opportunity.ts
  - actions/crm/get-opportunities.ts
- description: Activity, history, audit log and similarity actions.
  paths:
  - actions/crm/activities/
  - actions/crm/audit-log/
  - actions/crm/similarity/
  - lib/audit-log.ts
  - components/crm/activities/
  - components/crm/audit-log/
- description: Funnel stage gate, stage transitions, timers and automation jobs.
  paths:
  - lib/crm/approval-gate.ts
  - lib/crm/stage-transition.ts
  - lib/crm/funnel-timers.ts
  - lib/crm/funnel-settings.ts
  - lib/crm/stage-kinds.ts
  - lib/crm/client-activity.ts
  - lib/crm/auto-task.ts
  - inngest/functions/crm/qualified-cadence.ts
  - inngest/functions/crm/care-tasks.ts
  - inngest/functions/crm/kill-rule.ts
- description: Sales pages for accounts, contacts, leads, opportunities, pipeline, approvals and account tasks.
  paths:
  - app/[locale]/(routes)/crm/accounts/
  - app/[locale]/(routes)/crm/contacts/
  - app/[locale]/(routes)/crm/leads/
  - app/[locale]/(routes)/crm/opportunities/
  - app/[locale]/(routes)/crm/dashboard/
  - app/[locale]/(routes)/crm/approvals/
  - app/[locale]/(routes)/crm/tasks/
  - app/[locale]/(routes)/crm/components/line-items/
- description: Administration of users, CRM settings, funnel settings and audit log.
  paths:
  - actions/admin/users/
  - app/[locale]/(routes)/admin/users/
  - app/[locale]/(routes)/admin/crm-settings/
  - app/[locale]/(routes)/admin/funnel-settings/
  - app/[locale]/(routes)/admin/audit-log/
  - app/[locale]/(routes)/admin/layout.tsx
exclusions:
- description: The documentation site.
  paths:
  - apps/docs/
- description: Unit, integration and end-to-end tests and their mocks.
  paths:
  - __tests__/
  - tests/
  - __mocks__/
- description: Database migrations, seed data and the schema backup.
  paths:
  - prisma/migrations/
  - prisma/seeds/
  - prisma/initial-data/
  - prisma/schema.prisma.orig
- description: Build, container, deployment and maintenance scripts.
  paths:
  - scripts/
  - e2b/
  - Dockerfile
  - Dockerfile.release
  - docker-compose.yml
  - docker-compose.dev.yml
  - docker-compose-coolify.yml
  - docker-entrypoint.sh
- description: Shared UI primitives and email templates.
  paths:
  - components/ui/
  - emails/
- description: Design notes, plans and specs.
  paths:
  - docs/
unmapped:
- description: Contracts, contract line items, products, price lists, orders and products assigned to accounts.
  paths:
  - actions/crm/contracts/
  - actions/crm/contract-line-items/
  - actions/crm/products/
  - actions/crm/price-lists/
  - actions/crm/orders/
  - actions/crm/account-products/
  - app/[locale]/(routes)/crm/contracts/
  - app/[locale]/(routes)/crm/products/
  - app/[locale]/(routes)/crm/price-lists/
  - app/[locale]/(routes)/crm/orders/
- description: Campaigns, targets, target lists and target recycling.
  paths:
  - actions/crm/targets/
  - actions/crm/target-lists/
  - app/[locale]/(routes)/campaigns/
  - inngest/functions/campaigns/
  - inngest/functions/crm/recycle-targets.ts
- description: Contract and assigned-product renewal reminders.
  paths:
  - inngest/functions/crm/renewal-reminders.ts
- description: Projects, invoices, documents and reports modules.
  paths:
  - app/[locale]/(routes)/projects/
  - app/[locale]/(routes)/invoices/
  - app/[locale]/(routes)/documents/
  - app/[locale]/(routes)/reports/
  - actions/projects/
  - actions/documents/
  - actions/reports/
- description: Email and calendar sync and their linking to CRM records.
  paths:
  - app/[locale]/(routes)/emails/
  - inngest/functions/emails/
  - inngest/functions/calendar/
  - app/api/profile/calendar-connections/
  - app/api/crm/calendar/
- description: AI contact and target enrichment and record embeddings.
  paths:
  - lib/enrichment/
  - app/api/crm/contacts/enrich/
  - app/api/crm/contacts/enrich-bulk/
  - app/[locale]/(routes)/crm/contacts/enrichment/
  - inngest/functions/enrich-contact.ts
  - inngest/functions/embed-account.ts
- description: MCP server and API tokens.
  paths:
  - lib/mcp/
  - app/api/mcp/
  - lib/api-tokens.ts
  - actions/api-tokens.ts
  - actions/admin/users/revoke-api-tokens.ts
- description: Shared-secret endpoints that create leads and contacts from outside forms.
  paths:
  - app/api/crm/leads/create-lead-from-web/
  - app/api/crm/contacts/create-from-remote/
- description: Unified search, the CRM overview page and the main dashboard.
  paths:
  - actions/fulltext/
  - app/[locale]/(routes)/fulltext-search/
  - app/[locale]/(routes)/crm/page.tsx
  - app/[locale]/(routes)/crm/components/
- description: 'Profile settings and other administration pages: currencies, pricing, invoices, orders, plugins, services, LLM keys, calendar settings and mail to all users.'
  paths:
  - app/[locale]/(routes)/profile/
  - app/[locale]/(routes)/admin/currencies/
  - app/[locale]/(routes)/admin/pricing/
  - app/[locale]/(routes)/admin/invoices/
  - app/[locale]/(routes)/admin/orders/
  - app/[locale]/(routes)/admin/plugins/
  - app/[locale]/(routes)/admin/services/
  - app/[locale]/(routes)/admin/llm-keys/
  - app/[locale]/(routes)/admin/calendar-settings/
  - actions/admin/send-mail-to-all/
- description: Plugin system, plugin SDK and bundled plugins such as account protection and company registry lookup.
  paths:
  - plugins/
  - packages/
  - lib/plugins/
  - actions/crm/accounts/lookup-company.ts
limitations:
- description: First-user promotion to admin and the new sign-up email to admins depend on a sign-up callback whose invocation by the auth library could not be confirmed.
  paths:
  - lib/auth.ts
  - lib/new-user-notify.ts
---

# Coverage
