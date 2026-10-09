---
record_type: observation
site: eBay
page: Wireless Headphones search results
context: The eBay search for wireless headphones has the Under $18.00 price filter active, shows 26,000+ results, and displays Singapore as the shipping destination for the price-and-shipping sort. Sort is Best Match; the first visible listed prices are $13.19, $9.59, and $15.99.
trigger: a populated filtered results page has a sort control
action: "Select Price + Shipping: lowest first."
response:
  - "The sort control changes from Best Match to Price + Shipping: lowest first."
  - "The query remains wireless headphones, the URL retains `_udhi=18`, and the Under $18.00 filter chip remains visible."
  - "The first visible price-bearing listings appear in increasing listed-price order: $6.99, $9.19, and $10.00."
  - "The displayed result heading changes from 26,000+ to 19,000+ results; the reason for the change is unknown."
state: Wireless-headphones results under $18 with Best Match sorting → the same query and Under $18 filter with Price + Shipping ascending; the displayed result count changes.
intent: see lower-priced wireless-headphone listings first
purpose: "hypothesis — let shoppers order the current filtered results by price including shipping"
evidence:
  - evidence_class: observed
    url: https://www.ebay.com/sch/i.html?_nkw=wireless+headphones&_udhi=18&_sop=15
    page_title: Wireless Headphones for sale | eBay
    viewport: unknown
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open the public eBay search for wireless headphones, select Under $18.00, then open Sort and choose Price + Shipping: lowest first. Compare the query, active filter chip, sort label, result heading, and first visible prices."
    before: "The URL contains `?_nkw=wireless+headphones&rt=nc&_udhi=18`. The page shows 26,000+ results, an Under $18.00 filter chip, and Best Match sorting. The first visible listed prices are $13.19, $9.59, and $15.99."
    after: "The URL contains `?_nkw=wireless+headphones&_udhi=18&_sop=15`; the query and Under $18.00 filter chip remain, Sort shows Price + Shipping: lowest first, and the heading shows 19,000+ results. The first visible listed prices are $6.99, $9.19, and $10.00. Singapore remains the displayed shipping destination."
    screenshot: null
confidence: high
boundaries: []
counterexamples: []
---

## Notes

The lowest-price sort visibly changed the first listings while retaining the submitted query and active price constraint. The result heading changed from 26,000+ to 19,000+ and the URL no longer included `rt=nc`; the cause and effect on eligible items are unknown, so exact membership is not claimed. The first listing was Open Box and the third had both auction and Buy It Now prices, so only the displayed listed prices are reported.
