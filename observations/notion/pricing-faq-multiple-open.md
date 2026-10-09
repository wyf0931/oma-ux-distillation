---
record_type: observation
site: Notion
page: Pricing page Questions & answers
context: “How is pricing calculated for the paid plans?” is expanded and its answer is visible.
trigger: explicit activation of another collapsed FAQ question while an answer is already open
action: Activate “Can I change my payment method?”.
response:
  - The payment-method question enters an expanded state and its answer appears below it.
  - The pricing-calculation question and its answer remain expanded and visible.
  - The pricing page remains loaded at the same URL.
state: Two FAQ questions and answers are visible at once; opening the second does not close the first.
intent: view another pricing answer while retaining the first answer
purpose: "hypothesis — allow visitors to compare multiple answers without reopening prior items"
evidence:
  - evidence_class: observed
    url: https://www.notion.com/pricing
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Expand “How is pricing calculated for the paid plans?”; then activate “Can I change my payment method?” and inspect both question states and answer regions.
    before: The pricing-calculation question and answer are expanded; the payment-method question is collapsed.
    after: Both questions are expanded with their answers visible; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

This confirms that these two Notion pricing FAQ items can remain open simultaneously. It does not establish whether all FAQ sections on the site behave the same way.
