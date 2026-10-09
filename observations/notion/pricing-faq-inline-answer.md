---
record_type: observation
site: Notion
page: Pricing page Questions & answers
context: The Questions & answers section lists collapsed pricing questions.
trigger: explicit activation of a collapsed FAQ question
action: Activate “How is pricing calculated for the paid plans?”.
response:
  - The question enters an expanded state.
  - An answer appears directly below it, explaining that paid plans are charged per workspace member and guests are free with limited access.
state: The answer changes from hidden to visible while the pricing page remains loaded.
intent: understand how Notion's paid plan pricing is calculated
purpose: "hypothesis — answer a pricing question in place so visitors can continue exploring the pricing page"
evidence:
  - evidence_class: observed
    url: https://www.notion.com/pricing
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public Pricing page and activate “How is pricing calculated for the paid plans?” in Questions & answers.
    before: The pricing question appears as a collapsed disclosure triangle.
    after: The question is expanded and the associated answer is visible; the page URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The answer remained in the FAQ page context. Link destinations within other answers were not tested.
