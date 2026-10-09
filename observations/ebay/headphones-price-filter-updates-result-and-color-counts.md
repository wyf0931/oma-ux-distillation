---
record_type: observation
site: eBay
page: Wireless Headphones search results
context: The public eBay results page shows 150,000+ wireless-headphones listings; the header displays Singapore as the shipping destination. The Price facet offers an Under $18.00 option; the Color facet lists Black (105,029), Blue (16,481), Gold (4,213), and Gray (9,323).
trigger: a price range and counted color facets are visible alongside a submitted search result set
action: Select the Under $18.00 price facet.
response:
  - The URL adds `rt=nc` and `_udhi=18`.
  - The result heading changes from 150,000+ to 26,000+ results for wireless headphones.
  - Color counts update; Black changes from 105,029 to 17,599, Blue from 16,481 to 4,542, Gold from 4,213 to 772, and Gray from 9,323 to 1,809.
state: 150,000+ wireless-headphones results with a broad price range → 26,000+ results under $18 with updated color counts.
intent: limit the search results to lower-priced headphones
purpose: "hypothesis — show how available attributes change under the active price constraint"
evidence:
  - evidence_class: observed
    url: https://www.ebay.com/sch/i.html?_nkw=wireless+headphones&rt=nc&_udhi=18
    page_title: Wireless Headphones for sale | eBay
    viewport: unknown
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open the public eBay search results for wireless headphones in an isolated browser context. Note the displayed shipping destination. Record the 150,000+ result heading and the Price and Color facets. Select the visible Under $18.00 price link, then inspect the URL, result heading, and Color counts."
    before: "The URL is `https://www.ebay.com/sch/i.html?_nkw=wireless+headphones`; the page reports 150,000+ results and the header displays Singapore as the shipping destination. Color lists Black (105,029), Blue (16,481), Gold (4,213), and Gray (9,323)."
    after: "The URL adds `rt=nc&_udhi=18`; the page reports 26,000+ results. Color lists Black (17,599), Blue (4,542), Gold (772), and Gray (1,809)."
    screenshot: null
confidence: high
boundaries: []
counterexamples: []
---

## Notes

This records price-facet refinement and recalculated positive Color counts. The exposed Color choices all had positive counts; the page did not expose zero-count options, so this does not support or contradict `Zero-Count Facet Options Are Disabled`.
