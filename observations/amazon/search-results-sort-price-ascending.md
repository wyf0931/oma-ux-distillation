---
record_type: observation
site: Amazon
page: US search results for wireless headphones
context: "The results page shows the query ‘wireless headphones’, 1–16 of over 50,000 results, and Sort by set to Featured."
trigger: "The visitor changes the ordering of an already submitted search result set."
action: "Select Price: Low to High in Sort by."
response:
  - "Sort by changes to Price: Low to High."
  - "The URL gains the `s=price-asc-rank` sort parameter while retaining `k=wireless+headphones`."
  - "The first visible product cards are ordered by ascending displayed price ($1.99, $2.99, $3.15, and $3.49)."
  - "The result heading changes from over 50,000 to over 10,000 results; the reason and exact result-set change are unverified."
state: "The submitted query remains ‘wireless headphones’ while the selected sort changes from Featured to Price: Low to High and the visible product order changes."
intent: "See lower-priced products first."
purpose: "hypothesis — help visitors scan a broad product result set by a chosen price ordering."
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/s?k=wireless+headphones
    page_title: "Amazon.com : wireless headphones"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open Amazon search results for ‘wireless headphones’ in an isolated logged-out context, record the Featured sort and visible results, then select Price: Low to High."
    before: "The query is in the search field, Sort by shows Featured, and the results heading reports over 50,000 results."
    after: "Sort by shows Price: Low to High; the URL includes `s=price-asc-rank` and retains the query. The first visible result cards show prices $1.99, $2.99, $3.15, and $3.49. The heading reports over 10,000 results; the reason for that count change is unknown. No result was opened or purchased."
    screenshot: null
confidence: high
---

## Notes

The displayed prices, product mix, and rounded result counts are capture-time UI state. The observation supports only the visible ordering and retained query; it does not establish that the exact eligible result set stayed constant.
