---
record_type: observation
site: Vercel
page: Contact Sales email field
context: The public Contact Sales form is loaded with an empty Company email field; no contact fields have been submitted.
trigger: an invalid email value is entered and the field loses focus
action: Enter the synthetic value `not-an-email` in Company email and press Tab without submitting.
response:
  - The field is marked invalid.
  - "An inline description appears: ‘Please enter a valid email address’."
  - The Contact Sales page remains loaded at the same URL.
state: The empty Company email field changes to an invalid state with explicit correction guidance.
intent: provide a business email for a sales inquiry
purpose: "hypothesis — explain the accepted format before the visitor submits a sales request"
evidence:
  - evidence_class: observed
    url: https://vercel.com/contact/sales
    page_title: Contact Sales - Vercel
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On Contact Sales, enter `not-an-email` in Company email and move focus away with Tab; do not submit.
    before: Company email is empty; the form has not been submitted.
    after: Company email contains `not-an-email`, is marked invalid, and exposes the inline description “Please enter a valid email address”; URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The input was synthetic and no Contact Sales request was submitted. The correction behavior was not tested.
