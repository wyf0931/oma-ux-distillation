---
record_type: observation
site: Nike
page: Black Running Shoes category results
context: The Black Running Shoes category shows 140 products, Color reports one selected value (Black), and Sort By is Featured.
trigger: an active color filter and a sort control are visible on category results
action: "Choose Price: Low-High from Sort By."
response:
  - "The Sort By control changes to Price: Low-High."
  - The URL adds `sortBy=priceAsc` while the Black Running Shoes path remains.
  - Color continues to report one selected value and Black remains checked.
  - The displayed product count remains 140.
  - Visible price-bearing shoes are ordered upward from $29.97; gift-card cards without visible prices appear first.
state: Price order changes to ascending while the selected Black category filter and 140-product result context remain.
intent: view lower-priced black running shoes first
purpose: "hypothesis — let visitors sort a filtered product list without discarding its category constraint"
evidence:
  - evidence_class: observed
    url: https://www.nike.com/w/black-running-shoes-37v7jz90poyzy7ok
    page_title: Black Running Shoes. Nike.com
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open the public Running Shoes category, expand Color, select Black, and note the category URL, selected checkbox, count, Featured sort, and displayed prices. Open Sort By and choose Price: Low-High. Inspect the URL, selected filter, count, and price order."
    before: URL is `/w/black-running-shoes-37v7jz90poyzy7ok`; heading is Black Running Shoes (140); Color shows one selected value and Black is checked; Sort By is Featured. Visible prices include $157.97, $99.97, $37.97, and $55.97.
    after: "URL is `/w/black-running-shoes-37v7jz90poyzy7ok?sortBy=priceAsc`; heading and count remain Black Running Shoes (140); Color still shows one selected value and Black is checked; Sort By is Price: Low-High. The first visible price-bearing shoes are $29.97, $31.97, and $31.97 after gift-card cards without visible prices."
    screenshot: null
confidence: medium
---

## Notes

The interaction was repeated in the same isolated session after using browser Back. Both sorted states showed the Black filter selected, 140 products, and ascending prices for price-bearing shoes. The region suggestion overlay remained visible; it was not dismissed or changed. No product was opened.
