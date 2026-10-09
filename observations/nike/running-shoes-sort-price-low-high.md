---
record_type: observation
site: Nike
page: Running Shoes category results
context: "The Running Shoes category shows 245 products and a Sort By control. Initial visible products include Nike Pegasus Plus 2 at $170 and Nike Vomero Premium at $230."
trigger: "A product category page displays a sort control above its result list."
action: "Choose Price: Low-High from Sort By."
response:
  - "The sort control changes to Price: Low-High."
  - "The URL gains `sortBy=priceAsc` while the Running Shoes category remains active."
  - "The displayed product count remains 245."
  - "Two gift-card products without visible prices appear before priced shoes; the first price-bearing shoe cards are ordered from $29.97 to $30.97 to $31.97."
state: "The category result order changes from its initial featured order to ascending price for price-bearing products; the category path and displayed product count remain."
intent: "Browse lower-priced running shoes first."
purpose: "hypothesis — help visitors compare catalog items by an attribute they prioritize."
evidence:
  - evidence_class: observed
    url: https://www.nike.com/w/running-shoes-37v7jzy7ok
    page_title: "Running Shoes. Nike.com"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the public Nike Running Shoes category in an isolated context, open Sort By, and select Price: Low-High."
    before: "The Running Shoes page reports 245 products and displays the Sort By control. The first visible product cards include Pegasus Plus 2 at $170 and Vomero Premium at $230."
    after: "The URL is `/w/running-shoes-37v7jzy7ok?sortBy=priceAsc`; Sort By shows Price: Low-High and the count remains 245. Two gift cards without visible prices appear first, followed by price-bearing shoe cards at $29.97, $30.97, and $31.97."
    screenshot: null
confidence: high
---

## Notes

The region suggestion overlay remained visible during this session, but the Sort By menu accepted the selection and the page updated the selected sort and URL. This records only visible ordering and context preservation; the gift-card products have no displayed price for ordering comparison.
