---
record_type: observation
site: AMD
page: Processor Specifications table
context: "The Processor Specifications page shows the Family filter set to All and a table with 745 total entries; 25 rows are displayed per page."
trigger: "A populated processor specifications table and its Family filter are visible."
action: "Set the Family filter to Ryzen."
response:
  - "The Family control shows Ryzen."
  - "The dependent Series filter's available values narrow from 101 series across families to 18 Ryzen series, with All retained as the default value."
  - "The table changes from 745 total entries to 302 filtered entries; the first visible rows are Ryzen products."
  - "The page stays on the Processor Specifications listing and the URL remains unchanged."
state: "Family changes from All to Ryzen, the dependent Series options become Ryzen-only, and the table narrows from 745 to 302 entries while preserving the page context."
intent: "Limit the specification table to Ryzen processors."
purpose: "hypothesis — help visitors compare specifications within a selected processor family."
evidence:
  - evidence_class: observed
    url: https://www.amd.com/en/products/specifications/processors.html
    page_title: Processor Specifications
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the Processor Specifications page in a fresh isolated context and set the Family table filter from All to Ryzen. Do not select a product or activate Compare."
    before: "Family and Series are All; the Series control contains 101 series across families, including Sempron and Ryzen Threadripper values. The table reports Showing 1 to 25 of 745 entries. The comparison slots are empty."
    after: "Family is Ryzen and Series remains All; the Series control contains 18 Ryzen-family series. The table reports Showing 1 to 25 of 302 entries (filtered from 745 total entries). Visible rows list Ryzen products. The URL and comparison slots are unchanged."
    screenshot: null
confidence: high
---

## Notes

The selected Family value, Series options, and result count were confirmed in the accessibility snapshot and DOM. Before the selection, the Series control had 102 total options (All plus 101 series); afterward it had 19 total options (All plus 18 Ryzen series). Visible rows and the unchanged URL were checked. The comparison control was not used.
