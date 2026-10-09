---
record_type: observation
site: Apple
page: Global search overlay
context: The Search apple.com overlay is open with an empty search field and Quick Links visible.
trigger: text entry in the global search field
action: Enter “iPhone” without submitting the search.
response:
  - The field retains the query “iPhone”.
  - The overlay reports five Suggested Links and five Suggested Searches.
  - Suggested Links include Explore iPhone, Shop iPhone, iPhone Duo, iPhone 18 Pro, and iPhone Air.
  - Suggested Searches include query refinements such as iPhone Refurbished and iPhone All Cases.
state: Search assistance changes from default Quick Links to query-matched links and searches while the overlay remains open.
intent: find iPhone pages or refine the search
purpose: "hypothesis — offer direct destinations and query refinements before a full search submission"
evidence:
  - evidence_class: observed
    url: https://www.apple.com/
    page_title: Apple
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open Search apple.com in the global navigation and enter “iPhone” without pressing Enter or activating Submit search.
    before: The search overlay is open with an empty textbox and default Quick Links.
    after: The textbox contains “iPhone”; the accessibility snapshot reports five Suggested Links and five Suggested Searches; the page URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The suggestions and link destinations were visible in the accessibility snapshot. Keyboard selection, empty suggestions, and result behavior after submitting were not tested.
