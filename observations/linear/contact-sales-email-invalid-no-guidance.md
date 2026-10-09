---
record_type: observation
site: Linear
page: Public Contact Sales email field
context: The logged-out Contact Sales form is open with an empty Work email field; the form has not been submitted.
trigger: an invalid email value is entered and the field loses focus
action: Enter the synthetic value `not-an-email` in Work email, then press Tab without activating Send message.
response:
  - The accessibility snapshot marks the Work email field invalid.
  - No associated correction description, alert, or live error text appears after blur.
  - Focus moves to the next form control and the page remains on the same URL.
state: The empty Work email field changes to an invalid state without textual correction guidance.
intent: provide a work email for a sales inquiry
purpose: unknown
counterexamples:
  - "Direct counterexample to Inline Email Format Validation Feedback: a malformed value becomes invalid after blur but no correction message appears."
evidence:
  - evidence_class: observed
    url: https://linear.app/contact/sales
    page_title: Talk to sales – Linear
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the public Contact Sales form, enter `not-an-email` in Work email and press Tab; do not activate Send message.
    before: Work email is empty; Full name, Company size, requirements, and Send message controls are visible.
    after: Work email contains `not-an-email`; browser validity reports a type mismatch and the accessibility snapshot marks the field invalid. No associated description or alert is present; URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The invalid value was synthetic. The visual field style was not measured; the accessibility snapshot and DOM inspection confirmed invalid state with no associated text guidance. No form data was submitted.
