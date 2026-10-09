---
record_type: pattern
status: validated
name: Inline Email Format Validation Feedback
definition: When an email field receives a value that does not match the expected format, the interface marks the field invalid
  and provides associated correction guidance.
problem:
- A visitor may not know that an email value is malformed before continuing.
mechanism: Validate the email format locally and associate an inline message with the invalid field.
trigger:
- A malformed email value is entered and validation runs.
action:
- Enter a value that does not match the expected email format and move focus away from the field.
response:
- The field is marked invalid.
- A correction message appears near or is associated with the field.
use_when:
- The required input format can be checked locally and explained clearly.
avoid_when:
- Validity depends on server-side account existence or a remote eligibility check rather than format.
variants:
  - 'Inline text appears after blur: Netflix, Vercel, Stripe, Figma.'
examples:
- Netflix
- Vercel
- Stripe
- Figma
evidence:
- ../observations/netflix/signup-email-inline-validation.md
- ../observations/vercel/contact-sales-email-validation.md
- ../observations/stripe/contact-sales-email-validation.md
- ../observations/figma/contact-email-inline-validation.md
confidence: high
boundaries:
  - ../observations/airbnb/login-email-no-inline-feedback.md
counterexamples:
  - ../observations/notion/signup-email-invalid-state.md
  - ../observations/linear/contact-sales-email-invalid-no-guidance.md
---
## Cross-site invariant

Across Netflix, Vercel, Stripe, and Figma, entering a malformed email and moving focus away marked the field invalid and displayed correction guidance before submission.

## Boundaries and counterexamples

Notion and Linear are direct counterexamples to the text-guidance response. Both fields were marked invalid after blur without an explanatory message; Linear's browser validity state also reported an email type mismatch. Airbnb is a boundary: its logged-out phone-or-email field showed no invalid state after blur, and submit-time validation was not tested.

## Validation limits

Explicit correction text was directly observed on four independent public forms, and a meaningful boundary was checked. Two matched blur-validation cases (Notion and Linear) lacked text guidance, so this pattern is limited to the feedback variant that supplies a message. Subsequent clear-and-correction behavior is documented separately in [Email Validation Feedback Updates After Correction](email-validation-feedback-updates-after-correction.md); server-side validation remains untested.
