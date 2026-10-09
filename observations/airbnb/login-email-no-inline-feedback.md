---
record_type: observation
site: Airbnb
page: Logged-out login email field
context: The login page shows a blank “手机号或邮箱” (phone number or email) field and a Continue button.
trigger: text entry in the phone-or-email field followed by blur
action: Enter the synthetic value `not-an-email`, then move focus away without activating Continue.
response:
  - The field retains `not-an-email`.
  - No inline validation message or invalid state appears in the accessibility snapshot after blur.
  - The login page remains loaded at the same URL.
state: The input value changes, but no validation feedback is observed before submission.
intent: enter a sign-in identifier
purpose: unknown
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/login
    page_title: 登录/注册 - 爱彼迎
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the logged-out login page, enter `not-an-email` in 手机号或邮箱 and press Tab; do not activate Continue.
    before: The identifier field is empty and no validation message is visible.
    after: The field contains `not-an-email`; no inline error is visible, the URL is unchanged, and Continue remains available.
    screenshot: null
confidence: medium
---

## Notes

This only establishes that no immediate inline message appeared before submission. Validation may occur after Continue, which was not activated.
