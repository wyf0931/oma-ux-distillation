---
record_type: observation
site: Airbnb
page: Homepage search, empty Location field
context: "The Location searchbox is empty and focused. A Recommended destinations list is open beneath it."
trigger: "The visitor is focused in the empty Location searchbox while recommendations are visible."
action: "Press Tab once."
response:
  - "Keyboard focus moves from the Location searchbox to the Dates button labeled 添加日期."
  - "The Recommended destinations list remains visible."
  - "The URL remains https://zh.airbnb.com/."
state: "Tab advances from the Location field to Dates without focusing a recommendation."
intent: "Move keyboard focus to a destination shortcut or the next search control."
purpose: "hypothesis — sequence keyboard access through the search controls and suggested destinations."
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/
    page_title: "爱彼迎 | 度假屋、小木屋、海滨住宅等"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "In a fresh isolated context, dismiss the trip-total notice, focus the empty 地点 searchbox, confirm 推荐目的地 is open, then press Tab once. Do not activate any link or submit the search."
    before: "The empty 地点 searchbox has focus and 推荐目的地 links are visible."
    after: "Focus is on the 时间 添加日期 button; the recommendation links remain visible and the URL is unchanged."
    screenshot: null
confidence: high
---

## Notes

The resulting focus target was verified in both the accessibility snapshot and `document.activeElement`. No recommendation was activated, and no search was submitted. This records the observed tab order in one logged-out desktop session.
