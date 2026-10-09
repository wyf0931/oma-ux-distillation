---
record_type: observation
site: eBay
page: Wireless headphones search results
context: The public search results are narrowed to a maximum price of $1 and show 60 results. The Brand facet lists Bose (8), and the Color facet lists Black (56), Blue (5), Gold (1), Gray (5), Green (1), Pink (8), Purple (1), Red (6), Silver (4), and White (29).
trigger: a populated result set exposes counted Brand and Color facets
action: Select Bose in the Brand facet.
response:
  - The result heading changes from 60 to 8 results for wireless headphones.
  - The Color facet updates to Black (4), Orange (1), Pink (1), Red (1), and White (2).
  - The page remains on the wireless-headphones results and retains the maximum price of $1.
state: 60 wireless-headphones results with a $1 maximum and broad Color counts → 8 Bose results under the same price limit with updated Color options and counts.
intent: narrow the low-price results to Bose products
purpose: "hypothesis — recalculate other facet values after an additional constraint is applied"
evidence:
  - evidence_class: observed
    url: https://www.ebay.com/sch/i.html?_nkw=wireless+headphones&_udhi=1&_sop=15&rt=nc&Brand=Bose&_dcat=112529
    page_title: "Wireless Headphones for sale | eBay"
    viewport: unknown
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "In an isolated logged-out context, open eBay wireless-headphones results, set the maximum price to $1, and select Bose in Brand. Compare the result heading and Color facet before and after."
    before: "The price-limited page reports 60 results. Brand lists Bose (8). Color lists Black (56), Blue (5), Gold (1), Gray (5), Green (1), Pink (8), Purple (1), Red (6), Silver (4), and White (29)."
    after: "The page reports 8 results for wireless headphones. Color lists Black (4), Orange (1), Pink (1), Red (1), and White (2); the $1 maximum remains in the URL."
    screenshot: null
confidence: high
boundaries: []
counterexamples: []
---

## Notes

A later attempt to repeat the same Brand selection from the $1 price-limited state opened eBay's generic Error Page. That retry is not treated as evidence about the filter response. All Color values visible in the successful capture had positive counts; no zero-count option was observed, so this does not test whether eBay disables, hides, or leaves such values selectable.
