---
record_type: observation
site: Netflix
page: Tudum homepage
context: "The Fan Favorites carousel is at position 4 of 4, with KPop Demon Hunters, Not a Stranger, A Different World, and DAHMER in the final visible group. Previous items and Next items are both shown."
trigger: "The visitor is at the final position of the Fan Favorites sequence."
action: "Click Next items once."
response:
  - "The active position remains Page 4 of 4."
  - "The visible card group remains unchanged."
  - "Next items remains enabled after the click."
  - "The URL remains https://www.netflix.com/tudum."
state: "The Next action leaves the carousel at position 4 of 4; it does not wrap to the first position."
intent: "Try to advance to another group of featured titles."
purpose: "hypothesis — indicate that the carousel has reached its final group while preserving the sequence position."
evidence:
  - evidence_class: observed
    url: https://www.netflix.com/tudum
    page_title: "Netflix Tudum - Go behind the streams"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open Netflix Tudum in an isolated logged-out context, use Next items until Page 4 is active, note the visible cards and position indicator, then click Next items once."
    before: "Page 4 is the active position. The visible final group includes KPop Demon Hunters, Not a Stranger, A Different World, and DAHMER. Next items is enabled."
    after: "Page 4 remains active and the same card group remains visible. Next items is still enabled. The URL is unchanged."
    screenshot: null
confidence: high
boundaries:
  - "The control remains enabled at the final position even though clicking it produces no observed advancement."
counterexamples: []
---

## Notes

The click call completed successfully; the active position and visible group were checked afterward. This records a no-op at the terminal position for this session. It does not establish whether the enabled control is an intentional affordance, a site defect, or whether other input methods behave differently.
