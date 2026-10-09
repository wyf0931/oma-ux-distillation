---
record_type: observation
site: AMD
page: Homepage
context: The Products navigation menu is expanded with the Graphics tab selected and focused.
trigger: an expanded primary-navigation menu is open
action: Press Escape while the Graphics tab in the Products menu has focus.
response:
  - The Products menu closes.
  - The homepage remains loaded at the same URL.
state: The expanded Products menu changes to its collapsed state without navigating away.
intent: dismiss the open menu and return to the homepage context
purpose: "hypothesis — provide a keyboard way to dismiss the open destination menu"
evidence:
  - evidence_class: observed
    url: https://www.amd.com/en.html
    page_title: "AMD ׀ together we advance_AI"
    viewport: 1512x727
    browser: Chrome 154.0.0.0
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open Products, select Graphics so its tab has focus, then press Escape and inspect the accessibility snapshot.
    before: Products is expanded; Graphics is selected and focused; the Graphics destination panel is visible.
    after: Products is collapsed and its tabs and destination panel are absent; the homepage URL remains https://www.amd.com/en.html.
    screenshot: null
confidence: high
---

## Notes

Focus after dismissal was not verified. The menu was open and the Graphics tab selected in the preceding AMD Products menu observations.
