---
record_type: pattern
status: validated
name: Email Validation Feedback Updates After Correction
definition: When an email value changes after an invalid state appears, the interface clears feedback that no longer applies or replaces it with feedback for a remaining constraint.
problem:
- A stale error can mislead visitors after they edit or clear a field.
mechanism: Revalidate the changed value and reconcile the field's invalid state and message with the current value.
trigger:
- An email field is marked invalid or shows validation feedback for its current value.
action:
- Clear the value or replace it with a corrected value, then allow validation to run again.
response:
- The previous format error or invalid state clears when the value resolves that rule or the field is cleared.
- If another constraint remains, the message updates to describe it and the field stays invalid.
use_when:
- Email validation runs before form submission and can be repeated after edits.
avoid_when:
- Validation occurs only after server submission or depends on account existence that is not observable before submission.
variants:
- 'Clear control empties the field and clears invalid state: Notion.'
- 'Syntax-valid correction clears format feedback: Netflix, Vercel.'
- 'Syntax-valid correction reveals a work-email requirement: Stripe.'
examples:
- Notion
- Netflix
- Vercel
- Stripe
evidence:
- ../observations/notion/signup-email-clear-invalid.md
- ../observations/netflix/signup-email-correction-clears-validation.md
- ../observations/vercel/contact-sales-email-correction-clears-validation.md
- ../observations/stripe/contact-sales-email-correction-updates-validation.md
confidence: high
boundaries:
- ../observations/airbnb/login-email-no-inline-feedback.md
counterexamples: []
---
# Candidate: Email Validation Feedback Updates After Correction

**Status:** promoted to [Email Validation Feedback Updates After Correction](../patterns/email-validation-feedback-updates-after-correction.md) after the correction response was observed on four independent sites.

## Hypothesis

When a user changes the value of an invalid email field, the interface should reconcile the error state with the new value: clear feedback when the value resolves the current rule, or update it if a separate rule still fails.

## Supporting observations

- [Notion: Clear input after invalid value](../observations/notion/signup-email-clear-invalid.md) — clearing `not-an-email` emptied the field and removed its invalid state.
- [Netflix: correcting signup email](../observations/netflix/signup-email-correction-clears-validation.md) — replacing the malformed value with `reader@example.com` cleared the invalid state and message.
- [Vercel: correcting Contact Sales email](../observations/vercel/contact-sales-email-correction-clears-validation.md) — the same syntax-valid correction cleared the format error.
- [Stripe: correcting Contact Sales email](../observations/stripe/contact-sales-email-correction-updates-validation.md) — the format error changed to a work-email requirement; the field remained invalid.

## Boundary

- [Airbnb: login email without inline feedback](../observations/airbnb/login-email-no-inline-feedback.md) — no invalid state was observed after blur, so a correction response was not tested. Submit-time behavior remains unknown.

## Validation outcome

The feedback reconciliation mechanism was observed on four independent sites with three variants. Stripe shows that resolving one validation rule may reveal another. The sample only covers email fields and no form was submitted.
