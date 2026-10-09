---
record_type: observation
site: Porsche
page: Country Selector
context: The Country Selector page identifies Singapore as the current market; Europe is a collapsed region group.
trigger: explicit activation of a region group
action: Expand Europe.
response:
  - The Europe group enters an expanded state.
  - Country and language destinations appear, including France — Français, Belgium — Français, and Switzerland — Deutsch / Français / Italiano.
  - The selector page remains loaded.
state: Europe changes from collapsed to expanded and exposes its market/language options.
intent: browse available European markets and languages
purpose: "hypothesis — organize a long market list by region before visitors choose a destination"
evidence:
  - evidence_class: observed
    url: https://www.porsche.com/countries/?currentLocale=en-SG&src=navigation-header&referer=https%3A%2F%2Fwww.porsche.com%2Fsingapore%2Fen%2F%3Fcs_redirect%3D1
    page_title: Country Selector
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the Country Selector page, activate the collapsed Europe disclosure group.
    before: Europe is collapsed; no country destinations from the region are shown.
    after: Europe is expanded with market/language links; the current market remains Singapore and the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

Only the Europe group was opened. Search, other regions, and the selector's behavior after returning were not tested.
