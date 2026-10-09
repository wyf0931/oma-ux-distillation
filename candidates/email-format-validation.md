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
- 'Inline text appears after blur: Netflix, Vercel, Stripe.'
examples:
- Netflix
- Vercel
- Stripe
evidence:
- ../observations/netflix/signup-email-inline-validation.md
- ../observations/vercel/contact-sales-email-validation.md
- ../observations/stripe/contact-sales-email-validation.md
confidence: medium
boundaries:
  - ../observations/airbnb/login-email-no-inline-feedback.md
counterexamples:
  - ../observations/notion/signup-email-invalid-state.md
  - ../observations/linear/contact-sales-email-invalid-no-guidance.md
---
# Candidate: Email Format Validation

**Status:** promoted to [Inline Email Format Validation Feedback](../patterns/inline-email-format-validation-feedback.md) after explicit format-error messages were observed on Netflix, Vercel, and Stripe; retain this file as the hypothesis and validation record.

## Hypothesis

Some forms detect a malformed email before submission and may explain how to correct it or provide a way to clear the value.

Possible mechanism to test:

```text
malformed email → invalid field state → optional correction guidance or reset action
```

## Supporting observations

- [Netflix: signup email inline validation](../observations/netflix/signup-email-inline-validation.md) — after blur, the field was invalid and an inline “enter a valid email address” message appeared.
- [Vercel: Contact Sales email validation](../observations/vercel/contact-sales-email-validation.md) — after blur, the invalid Company email field exposed “Please enter a valid email address”.
- [Stripe: Contact Sales email validation](../observations/stripe/contact-sales-email-validation.md) — after blur, the invalid Work email field exposed a localized correction message.
- [Figma: Contact Us Work email validation](../observations/figma/contact-email-inline-validation.md) — after blur, the invalid Work email field exposed “Please provide a valid email address”.
- [Notion: clearing an invalid email](../observations/notion/signup-email-clear-invalid.md) — Clear input removed the malformed value and cleared its invalid state without submitting.

## Counterexample evidence

- [Notion: signup email invalid state](../observations/notion/signup-email-invalid-state.md) — the same malformed-value and blur action marked the field invalid but produced no textual correction guidance, contradicting the pattern's feedback response.
- [Linear: Contact Sales email invalid state](../observations/linear/contact-sales-email-invalid-no-guidance.md) — after blur, the browser/accessible state was invalid but no associated correction message or alert appeared.

## Boundary evidence

- [Airbnb: login email without inline feedback](../observations/airbnb/login-email-no-inline-feedback.md) — a malformed value remained in the phone-or-email field after blur with no visible validation message; Continue was not activated.

## Validation outcome

The invalid field plus explicit email-format guidance occurred on Netflix, Vercel, Stripe, and Figma. Notion and Linear are direct counterexamples to the text-guidance response; Airbnb is a boundary because submit-time validation remains unknown. No signup or Contact Sales form was submitted.

## Validation questions

- **Follow-up captured separately:** Notion's Clear input, Netflix and Vercel syntax-valid corrections, and Stripe's work-email follow-up are documented in [Email Validation Feedback Updates After Correction](email-validation-feedback-updates-after-correction.md).
- In the Netflix email field, no adjacent clear button was exposed when the error message appeared; the user may still be able to select and replace the text, which was not verified.
- Is validation triggered while typing, on blur, or only after activating Continue? Netflix flagged invalid while typing and displayed text after blur; Notion set invalid without text; Airbnb showed no immediate response.
- Do required-empty and malformed-value errors use distinct guidance?
- Does the same recovery behavior occur on other field types without submitting account information?
- Does Airbnb validate after Continue, or accept phone/email formats through a later step?
