---
record_type: observation
site: Amazon
page: Wireless headphones search results
context: Search results are filtered to Sony brand and Active Noise Cancellation; the page reports 1–16 of 216 results.
trigger: two query facets are active on the same result page
action: Remove the Sony brand filter while Active Noise Cancellation remains selected.
response:
  - The Sony constraint is removed from the active refinement parameters.
  - Active Noise Cancellation remains selected in the URL and as the remaining removable filter.
  - The query and results page remain open; the heading reports 1–16 of over 6,000 results.
  - The first visible result changes from the Sony-only set to a Soundcore product.
state: The result set broadens beyond Sony while retaining the Active Noise Cancellation constraint and search query.
intent: view noise-cancelling headphones from other brands
purpose: "hypothesis — let visitors revise one search constraint without discarding other active constraints"
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/s?k=wireless+headphones&rh=p_123%3A237204%2Cp_n_g-1003195531111%3A23746030011&dc&qid=1791473160&rnid=23746028011&ref=sr_nr_p_n_g-1003195531111_1&ds=v1%3A%2F8v9b00djIQlg9GBWlbHHrQSTVs5cqNpeKV5vHJWHIU
    page_title: "Amazon.com: Wireless Headphones - 237204 / Active Noise Cancellation"
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: In a fresh isolated logged-out search context, open wireless-headphone results, select Sony under Brands, then select Active Noise Cancellation under Noise Control. From the resulting page, activate Remove Sony filter. Inspect the URL, remaining active filters, result heading, and first visible product.
    before: Sony and Active Noise Cancellation are both active; the heading reports 1–16 of 216 results, and Sony products are visible.
    after: The active URL refinement contains Active Noise Cancellation without the Sony brand constraint. The page title and Remove link retain Active Noise Cancellation, the heading reports 1–16 of over 6,000 results, and the first visible result is Soundcore by Anker Q20i.
    screenshot: null
confidence: medium
---

## Notes

The result count is rounded after Sony is removed. The remaining Active Noise Cancellation constraint is supported by its URL parameter, page title, and visible Remove filter link. No product was opened.
