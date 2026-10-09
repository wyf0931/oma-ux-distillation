---
record_type: observation
site: Amazon
page: Search results for wireless headphones
context: Search results for “wireless headphones” are open; the Noise Control facet offers Active Noise Cancellation.
trigger: explicit selection of a facet on a submitted search results page
action: Select Active Noise Cancellation.
response:
  - The search URL gains the Active Noise Cancellation refinement parameter.
  - "The page title changes to ‘Amazon.com: Wireless Headphones - Active Noise Cancellation’."
  - A Remove Active Noise Cancellation filter link appears.
  - Matching products remain visible in the same results page.
state: The `wireless headphones` results page changes to an active-noise-cancellation-filtered state without leaving the search context.
intent: narrow wireless headphone results to active noise cancellation products
purpose: "hypothesis — let shoppers refine a broad product query by a relevant feature"
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/s?k=wireless+headphones
    page_title: "Amazon.com: Wireless Headphones - Active Noise Cancellation"
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Submit “wireless headphones” on Amazon, then select Active Noise Cancellation under Noise Control.
    before: Search results for “wireless headphones” are shown; Active Noise Cancellation is offered as a filter.
    after: The URL includes the Noise Control facet; the title names Active Noise Cancellation and a Remove filter link is visible. The displayed count remains rounded as “over 6,000”.
    screenshot: null
confidence: medium
---

## Notes

The page marked the filter as active and showed matching product content. The rounded result count did not visibly change; no claim is made about the exact number of results removed.
