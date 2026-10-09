---
record_type: observation
site: Netflix
page: Singapore landing page signup form
context: The logged-out landing page shows an empty email field and a Get Started button.
trigger: an invalid email value is entered and the field loses focus
action: Enter the synthetic value `not-an-email`, then press Tab without submitting the form.
response:
  - The field is marked invalid.
  - "An inline message appears: ‘请输入有效的电子邮件地址。’ (Please enter a valid email address.)"
  - Focus moves to the Get Started button; no account flow opens.
state: The empty email field changes to an invalid-value state with an associated error message.
intent: provide an email address to continue signup
purpose: "hypothesis — explain the input format needed before the visitor proceeds"
evidence:
  - evidence_class: observed
    url: https://www.netflix.com/sg-zh/
    page_title: Netflix 新加坡 — 在线观看电影和电视节目
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the logged-out landing page, enter `not-an-email` in the email field and move focus away with Tab; do not activate Get Started.
    before: The email field is empty and the Get Started button is visible.
    after: The field is marked invalid and shows the localized validation message; the page URL is unchanged and the form is not submitted.
    screenshot: null
confidence: high
---

## Notes

The input was synthetic and the form was not submitted. Correcting the value and validation recovery were not tested.
