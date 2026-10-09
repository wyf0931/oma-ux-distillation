---
record_type: pattern
status: validated
name: Email Validation Feedback Updates After Correction
definition: When an email value changes after an invalid state appears, the interface clears feedback that no longer applies or replaces it with feedback for a remaining constraint.
problem:
- A stale error can mislead visitors after they edit or clear a field.
- A syntactically valid value may still violate another form-specific rule.
mechanism: Revalidate the changed value and reconcile the field's invalid state and message with the current value.
trigger:
- An email field is marked invalid or shows validation feedback for its current value.
action:
- Clear the value or replace it with a corrected value, then allow validation to run again.
response:
- The previous format error or invalid state clears when the value resolves that rule or the field is cleared.
- If another constraint remains, the message updates to describe it and the field stays invalid.
- The form remains unsubmitted while the feedback changes.
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
## Cross-site invariant

Across four sites, changing an email value after an invalid state reconciled the feedback with the new value. Notion's Clear input emptied the field and removed its invalid state. Netflix and Vercel removed the format error after a syntax-valid correction. Stripe replaced the format error with a work-email requirement and kept the field invalid.

## Boundaries and counterexamples

Airbnb's logged-out phone-or-email field did not show an invalid state after blur. Since no prior validation feedback was visible, there was no correction state to observe; submit-time validation remains untested.

## Validation limits

These examples cover email fields only. Error recovery for other field types, server-side address checks, and behavior after a form submission were not tested. The sample email used for correction was synthetic and was never submitted.
