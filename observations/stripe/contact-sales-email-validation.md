---
record_type: observation
site: Stripe
page: Singapore Contact Sales email field
context: The public Contact Sales form is on step 1 with an empty Work email field.
trigger: an invalid email value is entered and the field loses focus
action: Enter the synthetic value `not-an-email` in Work email and press Tab without activating Continue.
response:
  - The field is marked invalid.
  - "An inline description appears: ‘请输入有效的电子邮件地址’."
  - The Contact Sales form remains on step 1 at the same URL.
state: The empty Work email field changes to an invalid state with explicit correction guidance.
intent: provide a work email for a sales inquiry
purpose: "hypothesis — explain the required format before a visitor proceeds to the next step"
evidence:
  - evidence_class: observed
    url: https://stripe.com/zh-sg/contact/sales
    page_title: Stripe | 联系我们的销售团队
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On Contact Sales step 1, enter `not-an-email` in Work email and move focus with Tab; do not activate Continue.
    before: Work email is empty; the first-step Continue button is visible.
    after: Work email contains `not-an-email`, is marked invalid, and has the inline message “请输入有效的电子邮件地址”; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The value was synthetic and the Contact Sales flow was not advanced.
