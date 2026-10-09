---
record_type: observation
site: AMD
page: Homepage Products menu category tabs
context: The Products menu is open with Processors selected and its grouped destinations visible.
trigger: explicit selection of a category tab within expanded navigation
action: Select Graphics.
response:
  - Graphics becomes the selected tab.
  - The Processors destination panel is replaced with grouped Graphics destinations under Workstations, Desktops, Laptops, and Resources.
  - The browser remains on the AMD homepage.
state: The selected product category changes from Processors to Graphics while the Products menu remains expanded.
intent: browse AMD graphics products and resources
purpose: "hypothesis — switch among large product categories without leaving the expanded menu"
evidence:
  - evidence_class: observed
    url: https://www.amd.com/en.html
    page_title: AMD ׀ together we advance_AI
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open Products in the AMD homepage navigation, then select the Graphics category tab.
    before: Products is expanded; Processors is selected and its destination panel is visible.
    after: Graphics is selected; the menu shows Workstations, Desktops, Laptops, and Resources links; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The category panel changed in place. The next step of selecting a Graphics destination was not tested.
