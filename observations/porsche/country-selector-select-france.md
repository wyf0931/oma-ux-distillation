---
record_type: observation
site: Porsche
page: Country Selector to France homepage
context: The Europe group is expanded and exposes the France — Français destination.
trigger: explicit selection of a market/language destination
action: Select France — Français.
response:
  - The browser navigates to the Porsche France homepage.
  - The homepage content is displayed in French.
  - The destination remains the homepage rather than a different page type.
state: The homepage changes from Singapore English to France French.
intent: view Porsche's homepage for the French market in French
purpose: "hypothesis — move visitors to an equivalent homepage in the chosen market and language"
evidence:
  - evidence_class: observed
    url: https://www.porsche.com/countries/?currentLocale=en-SG&src=navigation-header&referer=https%3A%2F%2Fwww.porsche.com%2Fsingapore%2Fen%2F%3Fcs_redirect%3D1
    page_title: Country Selector
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Expand Europe and activate the France — Français link.
    before: The Country Selector is open with Europe expanded; the France — Français destination is visible.
    after: The browser is on https://www.porsche.com/france/ with the page title Porsche France | Site officiel and French homepage content.
    screenshot: null
confidence: high
---

## Notes

The France destination changed both market and language. Persistence across visits and locale switching from non-homepage content were not tested.
