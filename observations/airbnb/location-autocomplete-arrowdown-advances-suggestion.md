---
record_type: observation
site: Airbnb
page: Homepage Location autocomplete
context: The Location combobox contains “Tokyo”; the suggestions list is open and “东京都, 日本” is already marked selected.
trigger: text suggestions are open and the Location combobox has focus
action: Press ArrowDown once.
response:
  - The combobox value changes from “Tokyo” to “新宿区, 东京都, 日本”.
  - The selected suggestion moves to Shinjuku, Tokyo.
  - The suggestions list remains open and the page URL stays on the homepage.
state: Keyboard ArrowDown advances the current suggestion selection and replaces the Location field value with the selected place.
intent: navigate the place suggestions by keyboard
purpose: "hypothesis — let visitors select a recognized destination without using a pointer"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/
    page_title: 爱彼迎 | 度假屋、小木屋、海滨住宅等
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Open the Airbnb homepage in a fresh isolated context, enter “Tokyo” in Location, note which suggestion is selected, then press ArrowDown once. Inspect the input value, selected suggestion, open list, and URL.
    before: Location contains “Tokyo”; “东京都, 日本” is marked selected in the open suggestions list.
    after: Location contains “新宿区, 东京都, 日本”; Shinjuku, Tokyo is selected; suggestions remain open; URL remains https://zh.airbnb.com/.
    screenshot: null
confidence: medium
---

## Notes

In this session, a Tokyo Metropolitan suggestion was already marked selected after text entry, before the explicit ArrowDown keypress. ArrowDown moved selection to Shinjuku. This observation does not establish which suggestion would be initially selected in other sessions.
