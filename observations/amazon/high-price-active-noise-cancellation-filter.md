---
record_type: observation
site: Amazon
page: Wireless headphone results with minimum price above $5,800
context: "The submitted query ‘wireless headphones’ shows 19 results, sorted Price: Low to High, with the minimum price set to $5,800 and no Noise Control facet selected."
trigger: a Noise Control facet is available beside the visible results
action: Select Active Noise Cancellation.
response:
  - The URL retains the query and price constraint and adds the Active Noise Cancellation value.
  - The result heading changes from 19 results to 1 result.
  - The remaining product title includes “Wired Audiophile Headphones”; its relationship to the selected Noise Control facet is not established from the listing alone.
state: 19 high-priced query results → 1 result with Active Noise Cancellation selected.
intent: narrow the high-priced headphone results to noise-cancelling options
purpose: "hypothesis — let visitors narrow an already constrained result set by a product attribute"
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/s?k=wireless+headphones&rh=p_36%3A580000-%2Cp_n_g-1003195531111%3A23746030011&s=price-asc-rank&dc&qid=1791481730&rnid=23746028011&ref=sr_nr_p_n_g-1003195531111_2&ds=v1%3ApEFvBkKAGPIHtRx%2FWCCh49Bb78x51wfh3zNHHqlb3GA
    page_title: "Amazon.com: Wireless Headphones - $5,800 & Above / Active Noise Cancellation"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open the wireless-headphone results with minimum price set to $5,800 and Price: Low to High sorting. Select Active Noise Cancellation in the Noise Control refinements and inspect the result heading and URL."
    before: "The query shows 19 results, the minimum price is $5,800, sorting is Price: Low to High, and no Noise Control value is selected."
    after: The URL includes the Active Noise Cancellation facet and the heading reports 1 result. The visible product title includes “Wired Audiophile Headphones”; the listing does not establish why it matched.
    screenshot: null
confidence: high
---

## Notes

The result membership and exact count are capture-session evidence. The product title's “Wired” wording appears inconsistent with the wireless query, but no product detail was opened, so no claim is made about its facet metadata. No item was opened or purchased.
