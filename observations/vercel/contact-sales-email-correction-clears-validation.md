---
record_type: observation
site: Vercel
page: Contact Sales email field
context: The Company email field contains `not-an-email` and shows the inline format-error message after blur.
trigger: an invalid email value and its inline format error are present
action: Replace the field value with the synthetic address `reader@example.com` and move focus away without submitting.
response:
  - The Company email field retains `reader@example.com`.
  - The invalid state and inline format-error description clear.
  - The Contact Sales page remains loaded at the same URL.
state: The invalid email state changes to a valid-format value with no inline error.
intent: correct the company email format before completing the inquiry
purpose: "hypothesis — keep validation feedback aligned with the current field value"
evidence:
  - evidence_class: observed
    url: https://vercel.com/contact/sales
    page_title: Contact Sales - Vercel
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Enter `not-an-email` in Company email and blur to expose its format error; select the existing value, replace it with `reader@example.com`, and blur again. Do not submit the form.
    before: Company email contains `not-an-email`, is marked invalid, and exposes “Please enter a valid email address”.
    after: Company email contains `reader@example.com` with no invalid state or format-error description; the page URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

`reader@example.com` is a synthetic address at the reserved example.com domain. The Contact Sales form was not submitted and no other fields were filled.
