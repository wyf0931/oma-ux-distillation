---
record_type: observation
site: Airbnb
page: Homepage Location autocomplete and Dates picker
context: Location contains the selected suggestion “新宿区, 东京都, 日本”; the autocomplete suggestions list is open and the search remains unsubmitted.
trigger: a place suggestion is selected in the focused Location combobox
action: Press Enter.
response:
  - The selected Location remains “新宿区, 东京都, 日本”.
  - The autocomplete list closes and the Dates picker opens.
  - The page remains on the homepage and no search results load.
state: Enter commits the selected place and advances search setup to the Dates picker without submitting the search.
intent: confirm the highlighted destination and continue setting up a trip search
purpose: "hypothesis — move the search flow to the next required trip detail after a destination is chosen"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/
    page_title: 爱彼迎 | 度假屋、小木屋、海滨住宅等
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: In the Location autocomplete, enter “Tokyo”, press ArrowDown once to select Shinjuku, Tokyo, then press Enter. Inspect the Location control, open panel, and URL.
    before: Location contains “新宿区, 东京都, 日本”; its autocomplete list is open and the URL is the homepage.
    after: Location remains “新宿区, 东京都, 日本”; the Dates picker opens; the URL remains the homepage and no results page opens.
    screenshot: null
confidence: medium
---

## Notes

No date or guest count was selected, no search was submitted, and no listing or booking flow was opened.
