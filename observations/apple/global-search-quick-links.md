---
record_type: observation
site: Apple
page: Global search overlay
context: Apple homepage is loaded and the global Search apple.com control is collapsed.
trigger: explicit activation of the global search control
action: Activate Search apple.com.
response:
  - A search overlay opens with an empty search field.
  - "A Quick Links section appears with five destinations: Find a Store, Apple Vision Pro, AirPods, Apple Intelligence, and Apple Trade In."
  - The homepage remains loaded at the same URL.
state: The search control changes from collapsed to expanded and exposes default Quick Links before query entry.
intent: begin a site search or choose a suggested destination
purpose: "hypothesis — offer common destinations before the visitor enters a query"
evidence:
  - evidence_class: observed
    url: https://www.apple.com/
    page_title: Apple
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public homepage in an isolated context and activate Search apple.com without typing.
    before: The global search control is collapsed and no search field or Quick Links overlay is visible.
    after: The search field is empty and the Quick Links section lists five destinations; the homepage URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The destination list was visible in the accessibility snapshot. Whether this list is personalized, ranked by popularity, or static was not tested.
