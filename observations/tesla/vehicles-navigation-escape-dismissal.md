---
record_type: observation
site: Tesla
page: Homepage primary navigation
context: The Vehicles navigation dialog is open after hovering over the Vehicles control.
trigger: keyboard dismissal while the navigation dialog is open
action: Press Escape.
response:
  - The Vehicles dialog closes.
  - The homepage remains loaded at the same URL.
state: The navigation dialog changes from open to closed without a page transition.
intent: dismiss the menu and return to the homepage content
purpose: "hypothesis — provide a keyboard path for closing the expanded navigation"
evidence:
  - evidence_class: observed
    url: https://www.tesla.com/
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Hover over Vehicles to open its navigation dialog, then press Escape and inspect the accessibility snapshot.
    before: The Vehicles navigation dialog is present with model destination links.
    after: The dialog is absent; the collapsed Vehicles control and homepage content are present at the original URL.
    screenshot: null
confidence: high
---

## Notes

The dialog closed after Escape. Focus return to the Vehicles control was not verified.
