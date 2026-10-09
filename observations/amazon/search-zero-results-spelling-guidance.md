---
record_type: observation
site: Amazon
page: US search zero-results state
context: Amazon search is submitted for the synthetic query `qzvqxjrn-97-yxw`.
trigger: submitted query returns no matching products
action: Submit the query `qzvqxjrn-97-yxw` from the homepage search field.
response:
  - The results page states “No results for your search query.”
  - Guidance says “Try checking your spelling or use more general terms”.
  - The query remains visible in the search field.
  - The page stays on search results; no product or checkout flow opens.
state: A submitted product search transitions to a no-results state with advice to broaden or correct the query.
intent: find products matching the query
purpose: "hypothesis — help shoppers recover from a query with no matching products"
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/s?k=qzvqxjrn-97-yxw&crid=1BKV5D8Z7OICZ&sprefix=qzvqxjrn-97-yxw%2Caps%2C417&ref=nb_sb_noss
    page_title: "Amazon.com : qzvqxjrn-97-yxw"
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Submit the synthetic query `qzvqxjrn-97-yxw` on the Amazon homepage search field.
    before: The homepage search field contains the synthetic query and has not been submitted.
    after: The results page reports no results and advises checking spelling or using more general terms.
    screenshot: null
confidence: high
---

## Notes

The query was synthetic and no product was opened. Other Amazon query spellings and correction suggestions were not tested.
