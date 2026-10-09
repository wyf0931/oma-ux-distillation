---
record_type: observation
site: Porsche
page: Singapore homepage to country selector
context: The Porsche Singapore homepage header exposes a “Change Region or Language” link.
trigger: explicit activation of the region/language control
action: Activate “Change Region or Language”.
response:
  - The browser navigates to a Country Selector page.
  - The page identifies Singapore as the current market.
  - A search field and collapsed region groups are available.
state: The visitor moves from the Singapore homepage to a dedicated market-selection page.
intent: choose a different Porsche market or language
purpose: "hypothesis — let visitors choose a market and its supported language from a dedicated selector"
evidence:
  - evidence_class: observed
    url: https://www.porsche.com/singapore/en/?cs_redirect=1
    page_title: Porsche Singapore | Official Website
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public Singapore homepage and activate Change Region or Language in the header.
    before: The Singapore homepage is loaded and the region/language link is visible.
    after: The browser is on a Country Selector page; Singapore is identified as the current market and search/region controls are visible.
    screenshot: null
confidence: high
---

## Notes

The selector URL preserves a referer back to the Singapore page. No market was chosen in this interaction.
