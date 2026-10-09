---
record_type: observation
site: eBay
page: US homepage search
context: The homepage search form has an empty query and All Categories selected.
trigger: a search form exposes a category selector before query submission
action: Select Consumer Electronics in the search category selector.
response:
  - The category selector changes from All Categories to Consumer Electronics.
  - The search field remains empty.
  - The page URL does not change and no results page opens.
state: Search scope changes in the homepage form while the query remains empty.
intent: set a product category before entering a search query
purpose: "hypothesis — let visitors limit a marketplace query to a product domain"
evidence:
  - evidence_class: observed
    url: https://www.ebay.com/
    page_title: "Electronics, Cars, Fashion, Collectibles & More | eBay"
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Open the public eBay US homepage in a fresh isolated context and select Consumer Electronics in the category selector. Do not enter or submit a query.
    before: The query field is empty and the category selector shows All Categories.
    after: The category selector shows Consumer Electronics, the query field remains empty, and the page URL stays https://www.ebay.com/.
    screenshot: null
confidence: medium
---

## Notes

The category control is directly adjacent to the query field and has an accessible name identifying it as the search category selector.
