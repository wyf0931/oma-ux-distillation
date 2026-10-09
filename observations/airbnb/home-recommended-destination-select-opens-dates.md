---
record_type: observation
site: Airbnb
page: Homepage search, recommended destination selection
context: The empty Location field is focused and the Recommended destinations list is open with Tokyo, Busan, and Perth.
trigger: a recommended destination is available from the empty Location search
action: Select the Tokyo recommendation.
response:
  - The Location combobox fills with Tokyo.
  - The date-selection calendar opens, with past dates disabled and available check-in dates shown.
  - The URL remains on the homepage; no search results load.
state: The empty destination field changes to Tokyo and search setup advances to date selection without submitting.
intent: set Tokyo as the trip destination
purpose: "hypothesis — guide a search from a destination choice to the next required trip detail"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/
    page_title: 爱彼迎 | 度假屋、小木屋、海滨住宅等
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public Airbnb homepage, dismiss the trip-total notice if shown, focus the empty Location searchbox, and select Tokyo under Recommended destinations. Do not submit the search.
    before: Location is empty; Recommended destinations offers Tokyo, Busan, and Perth; the homepage URL is https://zh.airbnb.com/.
    after: Location contains Tokyo; the calendar displays available check-in dates and disables past dates; the homepage URL remains unchanged.
    screenshot: null
confidence: high
---

## Notes

No date was selected and no trip search was submitted. The destination came from the default recommendation list rather than text entry.
