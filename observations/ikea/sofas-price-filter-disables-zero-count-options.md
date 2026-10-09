---
record_type: observation
site: IKEA
page: Sofas & sectionals price filter
context: The public US Sofas & sectionals page shows 225 items. Color includes Orange (1); Price shows a $0.00–$499.99 range with 33 products.
trigger: an available price range and other counted facets are visible on the result list
action: Select the $0.00–$499.99 price range.
response:
  - The URL adds `filters=f-price-buckets:PRICE_0_50000`.
  - The result count changes from 225 to 33 items.
  - The Color facet updates; Orange changes from 1 product to 0 products and its checkbox is disabled. Best seller also changes from 12 products to 0 products and is disabled.
state: 225 sofas with Orange and Best seller options available → 33 lower-priced sofas; zero-count Orange and Best seller choices are unavailable.
intent: browse lower-priced sofas
purpose: "hypothesis — prevent users from applying facet values with no matching products"
evidence:
  - evidence_class: observed
    url: https://www.ikea.com/us/en/cat/sofas-sectionals-fu003/?filters=f-price-buckets%3APRICE_0_50000
    page_title: Sofas & Couches - Modern & Affordable - IKEA
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Open the public US sofas category with no active filters and observe the 225-item count and Orange (1) quick filter. Expand Price, select the visible $0.00–$499.99 option by activating its label, then inspect the result count and Color and Best seller option counts and states.
    before: The page reports 225 items; the Color quick filters show Orange (1); the Price range offers $0.00–$499.99 with 33 products.
    after: The price option is selected, the URL contains the price bucket, and the page reports 33 items. Orange and Best seller each show 0 products and their checkboxes are disabled.
    screenshot: null
confidence: medium
---

## Notes

The zero-count options were visible in the accessibility snapshot as disabled. Neither option was clicked, and no zero-results page was opened. This is a single-site observation of preemptive option disabling, not evidence for a final reusable pattern.
