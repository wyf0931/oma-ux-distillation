---
record_type: observation
site: AMD
page: Homepage Products navigation
context: The AMD homepage shows the Products control collapsed in the primary navigation.
trigger: explicit activation of a top-level navigation control
action: Activate Products.
response:
  - Products enters an expanded state without changing the page URL.
  - "A tabbed set of product categories appears: Processors, Accelerators, Graphics, Adaptive SoCs/FPGAs/SOMs, and Software/Tools/Apps."
  - The selected Processors tab exposes grouped destinations such as Server CPUs and Business Systems.
state: The Products control changes from collapsed to expanded with a selected product-category panel.
intent: browse AMD products by category
purpose: "hypothesis — organize a large product catalog into categories and grouped destinations"
evidence:
  - evidence_class: observed
    url: https://www.amd.com/en.html
    page_title: AMD ׀ together we advance_AI
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public AMD homepage and activate Products in the primary navigation.
    before: Products is a collapsed primary-navigation button; no product-category menu is visible.
    after: Products is expanded with category tabs and the Processors panel; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The selected category's grouped links were visible in the accessibility snapshot. Switching to another category and selecting a destination were not tested.
