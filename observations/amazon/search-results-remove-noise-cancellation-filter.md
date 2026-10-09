---
record_type: observation
site: Amazon
page: Search results for wireless headphones with Active Noise Cancellation filter
context: The results page is filtered to Active Noise Cancellation; a Remove filter link is visible.
trigger: explicit removal of an active search facet
action: Activate “Remove Active Noise Cancellation filter to expand results”.
response:
  - The Active Noise Cancellation condition is removed from the search URL.
  - "The page title returns to ‘Amazon.com: Wireless Headphones’."
  - The displayed count changes from over 6,000 results to over 50,000 results.
  - An Apply Active Noise Cancellation filter link is available again.
state: The same wireless-headphones query changes from filtered results to a broader unfiltered result set.
intent: view results without the noise-cancellation constraint
purpose: "hypothesis — let visitors undo a search facet and restore broader results"
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/s?k=wireless+headphones&rh=p_n_g-1003195531111%3A23746030011
    page_title: "Amazon.com: Wireless Headphones - Active Noise Cancellation"
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On filtered wireless-headphones results, activate Remove Active Noise Cancellation filter to expand results.
    before: The page title names Active Noise Cancellation; over 6,000 results are shown and a Remove filter link is available.
    after: "The page title is Amazon.com: Wireless Headphones; over 50,000 results are shown and Active Noise Cancellation can be applied again."
    screenshot: null
confidence: high
---

## Notes

The filter was removed without leaving the result context. Counts are rounded values displayed at capture time.
