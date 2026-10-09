---
record_type: observation
site: Apple
page: Global search overlay
context: "The Search apple.com overlay is open with an empty search field focused and five Quick Links visible."
trigger: "Quick Links are visible while the empty search field has focus."
action: "Press Tab once."
response:
  - "Keyboard focus moves from the search field to the Find a Store Quick Link."
  - "The overlay remains open and the URL is unchanged."
state: "Tab moves focus from the empty query field to the first Quick Link without activating it."
intent: "Move keyboard focus to a common destination."
purpose: "hypothesis — make the default destinations reachable without entering a query."
evidence:
  - evidence_class: observed
    url: https://www.apple.com/
    page_title: Apple
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open apple.com in a fresh isolated context, activate Search apple.com, leave the query empty, and press Tab once from the focused search field. Do not activate the link."
    before: "The empty Search apple.com field is focused; Quick Links is visible and Find a Store is the first link."
    after: "Find a Store has keyboard focus; the overlay remains open and the URL stays https://www.apple.com/."
    screenshot: null
confidence: high
---

## Notes

The focus target was confirmed in both the accessibility snapshot and `document.activeElement`. The link was not opened.
