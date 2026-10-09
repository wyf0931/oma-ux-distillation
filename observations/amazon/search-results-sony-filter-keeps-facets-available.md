---
record_type: observation
site: Amazon
page: Wireless headphones search results
context: "The search results for wireless headphones show over 50,000 results. The Brands facet offers Sony, Beats, JBL, Bose, Apple, Sennheiser, and Skullcandy, and other facets are visible."
trigger: "A populated results page offers a Brands facet."
action: "Select the Sony brand filter."
response:
  - "The results heading changes to 1–16 of 402 results for wireless headphones."
  - "The URL adds the Sony brand constraint and the listing stays on the same query."
  - "Sony is shown as the active brand filter, while other brand choices and facets such as Connectivity remain available."
state: "The visible set narrows to Sony results while the search context and other filter choices remain available."
intent: "Narrow the headphone results to Sony products."
purpose: "hypothesis — let visitors combine a brand choice with other product refinements."
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/s?k=wireless+headphones
    page_title: "Amazon.com: Wireless Headphones"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the public Amazon results page for wireless headphones in an isolated logged-out context, then select Sony under Brands. Do not open a product or submit personal information."
    before: "The heading reports 1–16 of over 50,000 results. Brands offers Sony, Beats, JBL, Bose, Apple, Sennheiser, and Skullcandy; no brand is active."
    after: "The heading reports 1–16 of 402 results. The URL contains the Sony brand constraint; Sony is active and the other brand choices and Connectivity facet remain available."
    screenshot: null
confidence: high
---

## Notes

The selected brand, result count, URL, and remaining facet links were verified in the accessibility snapshot. Other brands remained available as additional refinements, so this is a boundary for the dependent-options candidate rather than a direct counterexample: the facets shown here behave as combinable dimensions. No product was opened.
