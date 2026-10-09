---
record_type: observation
site: Stripe
page: Singapore pricing page FAQ
context: The FAQ section lists collapsed questions, including “支付费用是如何计算的？” (How are payment fees calculated?).
trigger: explicit activation of a collapsed FAQ question
action: Activate “支付费用是如何计算的？”.
response:
  - The question control enters an expanded state.
  - An answer appears in a region associated with the question.
  - The answer explains that Stripe charges per transaction based on the payment method and includes a link to details about local payment-method fees.
state: The answer changes from hidden to visible while the pricing page remains loaded.
intent: understand how transaction fees are calculated
purpose: "hypothesis — let visitors read pricing details in context without navigating away from the FAQ"
evidence:
  - evidence_class: observed
    url: https://stripe.com/zh-sg/pricing
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public pricing page; in the FAQ section activate “支付费用是如何计算的？” and inspect the updated accessibility snapshot.
    before: The FAQ question appears as a collapsed expandable button.
    after: The button is expanded and its associated answer region with a further-details link is visible; the pricing URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The answer and its link were directly visible. Closing the question, opening multiple questions, and destination-link behavior were not tested.
