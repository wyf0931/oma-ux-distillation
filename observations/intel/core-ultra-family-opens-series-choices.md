---
record_type: observation
site: Intel
page: Product Specifications, Intel Core Ultra family
context: "The Product Specifications view is in the Processors panel, where Intel Core Ultra Processors appears alongside seven other processor families."
trigger: "A processor family is available as a product choice."
action: "Select Intel Core Ultra Processors."
response:
  - "The view changes to an Intel Core Ultra Processors panel and the URL hash becomes #@PanelLabel236800."
  - "Three series destinations appear: Intel Core Ultra Series 3, Intel Core Ultra Processors (Series 2), and Intel Core Ultra Processors (Series 1)."
  - "The Product Specifications page remains loaded."
state: "Selecting the Intel Core Ultra family replaces the family choices with series choices within that family."
intent: "Browse Intel Core Ultra processor series."
purpose: "hypothesis — expose the next compatible product choices after the visitor selects a processor family."
evidence:
  - evidence_class: observed
    url: https://www.intel.com/content/www/us/en/ark.html#@Processors
    page_title: "Intel® Product Specifications"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "In the Processors panel, select Intel Core Ultra Processors. Do not open a series destination."
    before: "The Processors panel lists Intel Core Ultra Processors, Intel Core Processors, Intel Processor, Intel Arc Processor, Intel Xeon Processors, Intel Atom Processor, Intel Pentium Processor, and Intel Celeron Processor."
    after: "The panel lists links for Intel Core Ultra Series 3, Series 2, and Series 1. The URL hash is #@PanelLabel236800; no series link was opened."
    screenshot: null
confidence: high
---

## Notes

This is an in-page taxonomy drilldown: the selection narrows the next available product choices to series within the chosen family. No product result page was opened.
