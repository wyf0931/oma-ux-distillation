---
record_type: observation
site: AMD
page: Processor Specifications table
context: "Family is Ryzen, Series is All, and the table reports 302 entries filtered from 745 total entries."
trigger: "An active Family filter can be cleared to All."
action: "Set the Family filter to All."
response:
  - "The Family control changes to All."
  - "The Series choices expand from 18 Ryzen series to 101 series across families, including Athlon and Ryzen Threadripper values."
  - "The table expands from 302 filtered entries back to 745 total entries."
  - "The URL remains unchanged and the comparison slots remain empty."
state: "Clearing Family restores the broader Series option set and the full processor result set."
intent: "Restore all processor families after narrowing the table to Ryzen."
purpose: "hypothesis — let visitors broaden product exploration by removing the upstream constraint."
evidence:
  - evidence_class: observed
    url: https://www.amd.com/en/products/specifications/processors.html
    page_title: Processor Specifications
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "In the Processor Specifications table, set Family to Ryzen. Then set Family back to All. Do not select a product or activate Compare."
    before: "Family is Ryzen, Series is All, the Series control contains 18 Ryzen-family series, and the table reports Showing 1 to 25 of 302 entries filtered from 745 total entries."
    after: "Family is All, the Series control contains 101 series across families, and the table reports Showing 1 to 25 of 745 entries. The URL and comparison slots remain unchanged."
    screenshot: null
confidence: high
---

## Notes

The restored Family value, Series options, table count, and URL were confirmed in the accessibility snapshot and DOM. This captures clearing the parent filter; no comparison was started.
