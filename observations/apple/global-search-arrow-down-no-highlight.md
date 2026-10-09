---
record_type: observation
site: Apple
page: Global search overlay
context: "The Search apple.com overlay is open with an empty search field focused and five Quick Links visible."
trigger: "Quick Links are visible while the empty search field has focus."
action: "Press ArrowDown once."
response:
  - "Focus remains in the empty Search apple.com field."
  - "No Quick Link receives a visible focus or selected state."
  - "The Quick Links remain visible and the URL is unchanged."
state: "ArrowDown leaves focus in the empty search field in this session."
intent: "Move keyboard focus or selection to a Quick Link."
purpose: "hypothesis — let keyboard visitors move from search input to common destinations."
evidence:
  - evidence_class: observed
    url: https://www.apple.com/
    page_title: Apple
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open apple.com in a fresh isolated context, activate Search apple.com, and press ArrowDown once without typing."
    before: "The empty search field is focused and Quick Links lists Find a Store, Apple Vision Pro, AirPods, Apple Intelligence, and Apple Trade In."
    after: "The input remains focused; no Quick Link is active or selected; the overlay remains open and the URL stays https://www.apple.com/."
    screenshot: null
confidence: high
---

## Notes

Focus was checked in the accessibility snapshot and through `document.activeElement`. No destination was activated and no query was entered.
