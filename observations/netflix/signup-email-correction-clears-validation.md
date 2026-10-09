---
record_type: observation
site: Netflix
page: Singapore landing page signup form
context: The email field contains `not-an-email` and shows an inline format-error message after blur.
trigger: an invalid email value and its inline format error are present
action: Replace the field value with the synthetic address `reader@example.com` and move focus away without submitting.
response:
  - The field retains `reader@example.com`.
  - The invalid state and inline format-error message clear.
  - The page URL remains unchanged and Get Started is not activated.
state: The invalid email state changes to a valid-format value with no inline error.
intent: correct the email format before continuing signup
purpose: "hypothesis — remove stale format feedback once the value satisfies the format check"
evidence:
  - evidence_class: observed
    url: https://www.netflix.com/sg-zh/
    page_title: Netflix 新加坡 — 在线观看电影和电视节目
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Enter `not-an-email` in the email field and blur to expose the format error; select the existing value, replace it with `reader@example.com`, and blur again. Do not activate Get Started.
    before: The email field contains `not-an-email`, is marked invalid, and has an inline message asking for a valid email address.
    after: The field contains `reader@example.com`; no invalid state or format-error message is exposed; the URL is unchanged and the form is not submitted.
    screenshot: null
confidence: high
---

## Notes

`reader@example.com` is a synthetic address at the reserved example.com domain. The field was corrected through keyboard selection and text entry; no account flow was opened.
