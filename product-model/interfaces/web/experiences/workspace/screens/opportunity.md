---
entities:
- entity: opportunity
  shows: [Name, Expected close date, Sales type, Sales stage, Budget, Currency, Next step, Description, Account, Assigned to, Created on]
  collects: [Name, Expected close date, Delivery deadline, Sales type, Sales stage, Budget, Currency, Expected revenue, Next step, Description, Account, Contact, Campaign, Assigned to]
- entity: quote-approval
  shows: [Note]
- entity: line-item
  shows: [Name, Quantity, Unit price, Discount type, Discount, Line total]
  collects: [Product, Name, Description, Quantity, Unit price, Discount type, Discount]
- entity: activity
  shows: [Type, Title, Date and time, Duration, Outcome, Email subject, Notes, Created by]
  collects: [Type, Title, Date and time, Duration, Outcome, Email subject, Notes]
- entity: audit-log-entry
  shows: [Action, Changes, Changed by, Changed on]
entryPoints:
- web: /crm/opportunities/{opportunityId}
references:
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/opportunities/[opportunityId]/page.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/opportunities/[opportunityId]/components/BasicView.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/opportunities/[opportunityId]/components/LineItemsSection.tsx
- kind: code
  role: implementation
  target: app/[locale]/(routes)/crm/opportunities/[opportunityId]/components/RequestApprovalButton.tsx
---

# Opportunity

One deal: details, quote approval badge and request, line items with their subtotal, activities, similar deals, its accounts, contacts and documents, and its History tab.
