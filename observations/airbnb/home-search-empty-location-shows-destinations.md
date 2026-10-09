---
record_type: observation
site: Airbnb
page: Homepage search, empty Location field
context: The homepage search bar shows an empty Location field alongside Dates and Guests; no destination query has been entered.
trigger: the empty Location searchbox is available
action: Activate the Location searchbox without typing.
response:
  - Focus moves to the empty searchbox and a “Recommended destinations” list appears.
  - The list includes Tokyo with “nightlife”, Busan with “popular beach destination”, and Perth with “popular beach destination”.
  - The query remains empty and the homepage URL is unchanged.
state: The empty Location field changes from idle to focused with query-independent destination choices.
intent: choose a destination without composing a search query
purpose: "hypothesis — offer common destinations as a path into trip search"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/
    page_title: 爱彼迎 | 度假屋、小木屋、海滨住宅等
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public Airbnb homepage, dismiss the trip-total information dialog if shown, and activate the empty Location searchbox without typing.
    before: The homepage search bar shows empty Location, Dates, and Guests controls; no Recommended destinations list is open.
    after: The empty Location searchbox is focused; Recommended destinations links for Tokyo, Busan, and Perth appear. The URL remains https://zh.airbnb.com/.
    screenshot: null
  - evidence_class: observed
    url: https://zh.airbnb.com/
    page_title: 爱彼迎 | 度假屋、小木屋、海滨住宅等
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: In a second fresh isolated context, dismiss the trip-total notice with 知道了 and activate the empty 地点 searchbox without typing.
    before: The searchbox is empty and no Recommended destinations list is open.
    after: The searchbox is focused and the same three recommended destinations appear; query and URL remain unchanged.
    screenshot: null
confidence: high
---

## Notes

The empty-field recommendation response was reproduced in a second isolated context. No destination was selected and no search was submitted. The homepage's separate popular-listing carousels remained in the page; they are not included as search shortcuts.
