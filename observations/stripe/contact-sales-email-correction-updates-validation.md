---
record_type: observation
site: Stripe
page: Singapore Contact Sales email field
context: The Work email field contains `not-an-email` and shows an inline format-error message after blur.
trigger: an invalid email value and its inline format error are present
action: Replace the field value with the synthetic address `reader@example.com` and move focus away without activating Continue.
response:
  - The Work email field retains `reader@example.com`.
  - The prior format-error message is replaced by a message requiring a valid work email; the field remains marked invalid.
  - The Contact Sales form remains on step 1 at the same URL.
state: The syntax error is replaced with a work-email eligibility error after the field value changes.
intent: correct the email value before continuing the sales inquiry
purpose: "hypothesis — revalidate the current value and surface any remaining constraint"
evidence:
  - evidence_class: observed
    url: https://stripe.com/zh-sg/contact/sales
    page_title: Stripe | 联系我们的销售团队
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Enter `not-an-email` in Work email and blur to expose the format error; select the existing value, replace it with `reader@example.com`, and blur again. Do not activate Continue.
    before: Work email contains `not-an-email`, is marked invalid, and has the localized message “请输入有效的电子邮件地址”.
    after: Work email contains `reader@example.com`; the message changes to “请输入有效的工作邮箱以继续” and the field remains invalid; the URL and step are unchanged.
    screenshot: null
confidence: high
---

## Notes

`reader@example.com` is a synthetic address at the reserved example.com domain. The address passes the observed syntax rule but does not satisfy Stripe's work-email requirement. The Continue action was not activated.
