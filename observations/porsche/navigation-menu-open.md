---
record_type: observation
site: Porsche
page: Singapore homepage primary navigation
context: The homepage header shows a Menu control; no navigation dialog is open.
trigger: explicit activation of the primary navigation menu control
action: Activate Menu.
response:
  - A modal navigation dialog opens over the homepage.
  - Models is expanded by default and model entries appear.
  - The dialog exposes destination groups including Models, Electric, Vehicle Purchase, Services, Experience, and Account.
state: Primary navigation changes from closed to an open modal while the homepage remains loaded.
intent: explore vehicle models and other Porsche destinations
purpose: "hypothesis — provide a grouped destination index without navigating away from the homepage"
evidence:
  - evidence_class: observed
    url: https://www.porsche.com/singapore/en/?cs_redirect=1
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public Singapore homepage in an isolated context, choose only necessary cookies, then activate Menu.
    before: Menu is visible in the header and the navigation modal is absent.
    after: A modal navigation region appears with grouped destinations and model entries; the homepage URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The open modal and its groups were directly visible in the accessibility snapshot. Selecting a destination was not tested.
