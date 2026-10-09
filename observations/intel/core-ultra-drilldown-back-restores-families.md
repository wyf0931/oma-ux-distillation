---
record_type: observation
site: Intel
page: Product Specifications, Intel Core Ultra series choices
context: "The Product Specifications panel shows Intel Core Ultra Series 3, Series 2, and Series 1 links; a Back control is visible."
trigger: "The visitor wants to return to the parent processor-family choices."
action: "Activate Back."
response:
  - "The Intel Core Ultra series links are replaced by the Processors family choices."
  - "The URL hash changes from #@PanelLabel236800 to #@Processors."
  - "The Product Specifications page remains loaded."
state: "The drilldown moves from the Core Ultra series level back to the processor-family level without leaving the page."
intent: "Choose a different processor family."
purpose: "hypothesis — let visitors move back up the product hierarchy and choose a different branch."
evidence:
  - evidence_class: observed
    url: https://www.intel.com/content/www/us/en/ark.html#@PanelLabel236800
    page_title: "Intel® Product Specifications"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open Intel Product Specifications, select Processors, select Intel Core Ultra Processors, then activate the Back control above the series list."
    before: "The Core Ultra panel shows links for Series 3, Series 2, and Series 1; the URL hash is #@PanelLabel236800."
    after: "The Processors panel again shows its processor-family choices; the URL hash is #@Processors and the page remains loaded."
    screenshot: null
confidence: high
---

## Notes

The Back control reverses the in-page drilldown. No series link or product result was opened.
