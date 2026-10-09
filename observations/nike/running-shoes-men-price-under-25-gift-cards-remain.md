---
record_type: observation
site: Nike
page: Black Running Shoes with $0–$25 and Gender filters
context: "The Black Running Shoes category has Color = Black, Shop by Price = $0–$25, Price: Low-High sorting, and 2 visible gift-card cards. The Gender filter is open."
trigger: a Gender filter option is available on the current category results
action: Select Men under Gender.
response:
  - The URL path changes to `/mens-0-25-black-running-shoes-37v7jz90poyz90wvyznik1zy7ok` and keeps `sortBy=priceAsc`.
  - The page title changes to “Mens $0 - $25 Black Running Shoes” and the result count remains 2.
  - The visible cards remain Nike Digital Gift Card and Nike Gift Card; no no-results message or recovery action appears.
state: 2 gift-card cards in Black Running Shoes with a $0–$25 range → the same two cards in the Men's category path with the same range.
intent: view men's black running shoes in the selected price range
purpose: "hypothesis — narrow a product category by audience; the gift cards' persistence may be unrelated to the shoe results"
evidence:
  - evidence_class: observed
    url: https://www.nike.com/w/mens-0-25-black-running-shoes-37v7jz90poyz90wvyznik1zy7ok?sortBy=priceAsc
    page_title: Mens $0 - $25 Black Running Shoes. Nike.com
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open Black Running Shoes, sort Price: Low-High, select the $0–$25 Shop by Price range, then expand Gender and select Men. Compare the URL, heading, count, and first visible cards."
    before: The URL contains `/0-25-black-running-shoes` and `sortBy=priceAsc`; Shop by Price shows one selected range, Color shows one selected value, the heading count is 2, and the visible cards are Nike gift cards.
    after: The URL contains `/mens-0-25-black-running-shoes` and retains `sortBy=priceAsc`; the heading count remains 2 and the same two gift-card products remain visible. No no-results message appears.
    screenshot: null
confidence: medium
---

## Notes

The two cards do not show product prices. This capture does not establish whether the gift cards count as men's shoe matches or why they remain after the Gender choice. It is a boundary for empty-state research, not a zero-result observation or a direct counterexample to result refinement.
