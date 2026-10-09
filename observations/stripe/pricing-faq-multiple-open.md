---
record_type: observation
site: Stripe
page: Singapore pricing page FAQ
context: The FAQ item “支付费用是如何计算的？” is expanded and its answer is visible.
trigger: explicit activation of another collapsed FAQ question while an answer is already open
action: Activate “我会被征税吗？” (Will I be taxed?).
response:
  - The second question enters an expanded state and its answer appears inline.
  - The first question and its answer remain expanded and visible.
  - The pricing page remains loaded at the same URL.
state: Two FAQ questions and answers are visible at the same time; opening the second does not close the first.
intent: view another pricing answer while retaining the first answer
purpose: "hypothesis — allow visitors to compare multiple supporting answers without reopening prior items"
evidence:
  - evidence_class: observed
    url: https://stripe.com/zh-sg/pricing
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Expand “支付费用是如何计算的？”; then activate “我会被征税吗？” and inspect both question states and answer regions.
    before: The fee-calculation question and answer are expanded; the tax question is collapsed.
    after: Both questions are expanded with their answers visible; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

This observation establishes that these two Stripe FAQ items can remain open simultaneously. It does not establish whether every FAQ section on the site behaves the same way.
