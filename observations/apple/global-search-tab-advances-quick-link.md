---
record_type: observation
site: Apple
page: Global search overlay
context: "The Search apple.com overlay is open with an empty query. Find a Store, the first Quick Link, has keyboard focus."
trigger: "Keyboard focus is on the first Quick Link in the open search overlay."
action: "Press Tab once."
response:
  - "Keyboard focus advances to Apple Vision Pro, the second Quick Link."
  - "The overlay remains open and the homepage URL is unchanged."
state: "Tab advances focus from the first to the second Quick Link without activating either link."
intent: "Move keyboard focus to the next common destination."
purpose: "hypothesis — provide sequential keyboard access through the default destinations."
evidence:
  - evidence_class: observed
    url: https://www.apple.com/
    page_title: Apple
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open apple.com in a fresh isolated context, activate Search apple.com, press Tab from the search field to focus Find a Store, then press Tab once more. Do not activate either link."
    before: "Find a Store has keyboard focus; the empty search overlay and five Quick Links are open."
    after: "Apple Vision Pro has keyboard focus; the overlay and homepage URL remain unchanged."
    screenshot: null
confidence: high
---

## Notes

The focus target was confirmed in both the accessibility snapshot and `document.activeElement`. No link was opened and no query was entered.
