---
record_type: observation
site: Amazon
page: Wireless headphones search results
context: The results are filtered to a minimum price of $5,800; Sort by is Featured and the page reports 13 results.
trigger: an active price range and a sort control are visible on the result page
action: "Choose Price: Low to High."
response:
  - "The Sort by control changes from Featured to Price: Low to High."
  - The query and `low-price=5800` filter remain in the URL.
  - The Minimum price slider remains at $5,800.
  - Visible products are ordered from $5,815, $5,999, $6,080, and $6,152 upward.
  - The results heading reports 19 results, compared with 13 before the sort.
state: Price order changes to ascending while the query and minimum price filter remain active.
intent: view the least expensive results within the selected high-price range
purpose: "hypothesis — let visitors change ordering without discarding their query or active filter"
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/s?k=wireless+headphones&qid=1791480558&rnid=386442011&ref=sr_nr_p_36_0_0&low-price=5800&high-price=
    page_title: "Amazon.com: Wireless Headphones - $5,800 & Above"
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open Amazon wireless-headphone results with a minimum price of $5,800. Note the Featured sort, query, price slider values, result count, and visible product prices. Set Sort by to Price: Low to High and inspect the URL, sliders, count, and first products."
    before: The URL contains `low-price=5800`; Minimum price is $5,800, Maximum price is $6,600+, Sort by is Featured, and the heading reports 13 results.
    after: "The URL contains both `low-price=5800` and `s=price-asc-rank`; Sort by is Price: Low to High; Minimum price remains $5,800; the first visible prices are $5,815, $5,999, $6,080, and $6,152. The heading reports 19 results."
    screenshot: null
confidence: medium
---

## Notes

The result count changed from 13 to 19 after sorting, and the Maximum price slider endpoint changed from $6,600+ to $12,900+. The reason is unknown, so no claim is made that sorting preserved identical result membership. The query, minimum price constraint, and ascending order are directly visible in the after-state.
