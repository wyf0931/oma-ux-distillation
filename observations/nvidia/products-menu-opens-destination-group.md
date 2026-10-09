---
record_type: observation
site: NVIDIA
page: GeForce graphics card comparison
context: The comparison page is open and the global Products menu is collapsed.
trigger: click on the Products navigation item
action: Click Products in the primary navigation.
response:
  - The Products menu expands and exposes links grouped under Graphics Cards & Desktops, Laptops, and Other Products.
  - The current comparison page remains open and its URL does not change.
state: The Products navigation item changes from collapsed to expanded while the comparison page stays active.
intent: find a GeForce product or product family
purpose: "hypothesis — let visitors inspect product destinations from the comparison context"
evidence:
  - evidence_class: observed
    url: https://www.nvidia.com/en-us/geforce/graphics-cards/compare/
    page_title: Compare Current and Previous GeForce Series of Graphics Cards | NVIDIA
    viewport: 1280x727 CSS pixels
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the GeForce comparison page and click Products in the primary navigation.
    before: The Products menu item is collapsed and no destination links are exposed beneath it in the navigation snapshot.
    after: The expanded menu exposes product links including GeForce RTX 50 Series, GeForce RTX 5090, RTX 5080, RTX 5070 Family, and GeForce RTX 50 Series Laptops; the comparison URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The page's comparison matrix was static in the inspected state. This observation records only the primary navigation response. No destination link was opened.
