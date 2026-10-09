---
record_type: observation
site: Tesla
page: Homepage primary navigation
context: The Vehicles control is visible in the homepage navigation and its menu is collapsed.
trigger: pointer hover over a top-level navigation control
action: Hover over Vehicles.
response:
  - A navigation dialog opens without changing the page URL.
  - The dialog exposes vehicle destinations including Model 3, Model Y, Cybertruck, Model S, and Model X.
  - Model 3, Model Y, and Cybertruck each show Learn and Order links.
state: Vehicles navigation changes from collapsed to expanded while the homepage remains loaded.
intent: inspect available vehicle models and routes
purpose: "hypothesis — let visitors preview vehicle destinations and entry points from the homepage navigation"
evidence:
  - evidence_class: observed
    url: https://www.tesla.com/
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public homepage in an isolated context, reject optional cookies, then hover over Vehicles in the primary navigation.
    before: Vehicles appears as a collapsed primary-navigation control.
    after: A dialog with vehicle destinations and Learn / Order links appears; the homepage URL remains https://www.tesla.com/.
    screenshot: null
confidence: high
---

## Notes

The menu was opened through pointer hover. Click, keyboard, and touch behavior were not tested in this observation.
