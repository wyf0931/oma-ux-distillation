---
record_type: observation
site: Intel
page: Product Specifications category selection
context: "The Intel Product Specifications page shows a Select your product section with categories including Processors, Graphics, Chipsets, Wireless, and Memory and Storage."
trigger: "The visitor chooses a product category from the specification catalog."
action: "Select Processors."
response:
  - "The Product Specifications view changes to a Processors panel and the URL hash becomes #@Processors."
  - "The panel exposes processor-family choices: Intel Core Ultra, Intel Core, Intel Processor, Intel Arc Processor, Intel Xeon, Intel Atom, Intel Pentium, and Intel Celeron."
  - "The page remains within Product Specifications."
state: "The broad product-category choices are replaced in place by processor-family choices scoped to Processors."
intent: "Browse Intel processor products."
purpose: "hypothesis — reduce a broad product catalog to relevant processor families before presenting model series."
evidence:
  - evidence_class: observed
    url: https://www.intel.com/content/www/us/en/ark.html
    page_title: "Intel® Product Specifications"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open Intel Product Specifications in an isolated context and select Processors under Select your product."
    before: "Select your product lists Processors, Graphics, Chipsets, Wireless, Ethernet Products, Server Products, Memory and Storage, and I/O Products."
    after: "The Processors panel lists eight processor families; the URL hash is #@Processors and the page title remains Intel® Product Specifications."
    screenshot: null
confidence: high
---

## Notes

The Processor family tiles were exposed as custom clickable elements in the page DOM. This capture records the category-to-family choice step only; the subsequent Core Ultra-to-series step is recorded separately.
