---
singleton: true
references:
- kind: code
  role: implementation
  target: prisma/schema.prisma
- kind: code
  role: implementation
  target: lib/crm/funnel-timers.ts
---

# Funnel settings

The instance's one set of timings for the sales funnel's automatic follow-up; each value is a whole number of days.

## Information kept

- **Silent deal limit** — days without client activity after which a quote-stage deal is closed; 45 by default
- **Follow-up cadence** — the timing of the five quote follow-up touches: business days to the first, then days between touches
- **Care check-in delay** — days after entering a care stage before the check-in task; 30 by default
- **Referral ask delay** — days after entering a care stage before the referral-ask task; 90 by default
- **Quarterly check-in interval** — days between quarterly check-in tasks; 90 by default
- **Quarterly check-in count** — how many quarterly check-in tasks follow; 8 by default
- **Renewal window** — how far ahead renewal tasks are created; 30 days by default
- **Recycle delay** — days after a finished campaign sequence before a silent target is recycled; 90 by default
