---
record_type: observation
site: Airbnb
page: Homepage search, empty Location field
context: "The Location searchbox is empty and focused. A Recommended destinations list is open beneath it."
trigger: "Recommended destinations are visible while the empty Location searchbox has focus."
action: "Press ArrowDown once."
response:
  - "Focus remains on the Location searchbox."
  - "No recommendation receives a visible active or selected state in the accessibility snapshot or inspected DOM."
  - "The recommendation list remains open and the URL is unchanged."
state: "ArrowDown leaves the empty search and recommendation state unchanged in this session."
intent: "Move keyboard focus or selection to a recommended destination."
purpose: "hypothesis — allow keyboard visitors to choose a destination from the default suggestions."
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/
    page_title: "爱彼迎 | 度假屋、小木屋、海滨住宅等"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "In a fresh isolated context, dismiss the trip-total notice, focus the empty 地点 searchbox, and press ArrowDown once. Do not activate a destination."
    before: "The empty 地点 searchbox has focus and 推荐目的地 links are visible."
    after: "The input retains focus; no destination is reported active or selected; the links remain visible and the URL stays https://zh.airbnb.com/."
    screenshot: null
confidence: high
---

## Notes

The focus target was checked with the accessibility snapshot and `document.activeElement`. The visible recommendation links had no observed active or selected state after ArrowDown. This is one logged-out desktop session; no destination was activated.
