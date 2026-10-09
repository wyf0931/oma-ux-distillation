---
record_type: observation
site: Nike
page: Black Running Shoes with Shop by Price expanded
context: "The Black Running Shoes category is sorted Price: Low-High. Shop by Price has $0–$25 selected and the page shows 2 products."
trigger: another price range is available while the current price range remains selected
action: Select the $25–$50 price range without removing $0–$25.
response:
  - Shop by Price reports two selected ranges; $0–$25 and $25–$50 are both checked.
  - The result count changes from 2 to 28.
  - "The Black Running Shoes category and Price: Low-High sort remain active in the URL."
state: 2 products with $0–$25 selected → 28 products with $0–$25 and $25–$50 selected.
intent: include the next price range while keeping the current range selected
purpose: "hypothesis — allow visitors to combine adjacent price ranges within a price facet"
evidence:
  - evidence_class: observed
    url: https://www.nike.com/w/black-running-shoes-37v7jz3f27bz90poyzy7ok?sortBy=priceAsc
    page_title: Black Running Shoes. Nike.com
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open the public Black Running Shoes page with Price: Low-High sorting. Select $0–$25 in Shop by Price, then select $25–$50 without clearing the first range. Inspect selected checkboxes, URL, and result count."
    before: URL contains the Black Running Shoes category and `sortBy=priceAsc`; Shop by Price reports one selected range, $0–$25, and the page count is 2. The two visible products are gift cards without displayed prices.
    after: URL remains in the Black Running Shoes category with `sortBy=priceAsc`; Shop by Price reports two selected ranges, both $0–$25 and $25–$50 are checked, and the page count is 28.
    screenshot: null
confidence: medium
---

## Notes

No product was opened or purchased. This shows same-group range accumulation on Nike; the initial two gift cards had no displayed price, so their price-range membership is not established from card text alone.
