---
appliesTo:
- type: capability
  id: create-contact
- type: capability
  id: create-lead
- type: capability
  id: create-opportunity
- type: capability
  id: edit-lead
references:
- kind: code
  role: implementation
  target: actions/crm/leads/create-lead.ts#createLead
- kind: code
  role: implementation
  target: actions/crm/opportunities/create-opportunity.ts#createOpportunity
---

# A person assigned a new record by someone else is emailed

When someone creates a contact, lead or opportunity assigned to another person, or reassigns a lead, the assignee gets an email in their language with a link to the record.
