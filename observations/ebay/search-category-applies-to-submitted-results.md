---
record_type: observation
site: eBay
page: US marketplace search results
context: The search form contains “wireless headphones” with Consumer Electronics selected as its category.
trigger: submission of a query with a search category selected
action: Submit “wireless headphones” while Consumer Electronics is selected.
response:
  - The results URL includes `_sacat=293` for Consumer Electronics.
  - The page title reads “Wireless Headphones in Consumer Electronics for sale | eBay”.
  - The results heading reports 160,000+ results for wireless headphones.
  - The Category filter identifies Consumer Electronics and lists product subcategories.
  - The search field retains “wireless headphones”, while the header category selector displays All Categories again.
state: The submitted query opens results scoped to Consumer Electronics even though the header selector resets to All Categories.
intent: find wireless headphones in Consumer Electronics listings
purpose: "hypothesis — carry a preselected marketplace category into the submitted result scope"
evidence:
  - evidence_class: observed
    url: https://www.ebay.com/
    page_title: "Electronics, Cars, Fashion, Collectibles & More | eBay"
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: In a fresh isolated context, select Consumer Electronics in the eBay homepage search form, enter “wireless headphones”, and click Search. Inspect the URL, page title, result heading, category filter, and header selector after results load.
    before: The homepage search field contains “wireless headphones” and the category selector shows Consumer Electronics; the query has not been submitted.
    after: The URL is https://www.ebay.com/sch/i.html?_nkw=wireless+headphones&_sacat=293&_from=R40&_trksid=p4624852.m570.l1313. The title says “Wireless Headphones in Consumer Electronics for sale | eBay”, the heading says “160,000+ results for wireless headphones”, and the category filter identifies Consumer Electronics. The query remains in the search field; the header selector now shows All Categories.
    screenshot: null
confidence: medium
---

## Notes

The first Search activation in the same isolated context opened eBay's generic error page. Returning to the homepage and repeating the same Consumer Electronics search succeeded. A later All Categories submission in that context also opened the generic error page, so no direct broad-versus-scoped result-count comparison is claimed. The successful scoped state is supported by its URL, page title, and Category filter.
