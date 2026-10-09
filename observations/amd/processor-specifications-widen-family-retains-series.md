---
record_type: observation
site: AMD
page: Processor Specifications table
context: Family is Ryzen, Series is Ryzen 9000 Series, and the table reports 15 matching entries.
trigger: a selected child value remains compatible when its parent scope can be widened
action: Set Family to All while keeping Series set to Ryzen 9000 Series.
response:
  - Family changes from Ryzen to All.
  - Series remains set to Ryzen 9000 Series.
  - The table remains at 15 entries filtered from 745 total entries.
  - The URL remains unchanged.
state: The parent scope widens while the valid child filter remains active and the matching result set stays visible.
intent: broaden family browsing without losing the selected processor series
purpose: "hypothesis — preserve a valid downstream choice when the visitor broadens its parent scope"
evidence:
  - evidence_class: observed
    url: https://www.amd.com/en/products/specifications/processors.html
    page_title: Processor Specifications
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: On the Processor Specifications table, set Family to Ryzen and Series to Ryzen 9000 Series. Then set Family to All. Inspect both filter values, the table count, and the URL. Do not select a product or activate Compare.
    before: Family is Ryzen, Series is Ryzen 9000 Series, and the table reports Showing 1 to 15 of 15 entries filtered from 745 total entries.
    after: Family is All, Series remains Ryzen 9000 Series, and the table still reports Showing 1 to 15 of 15 entries filtered from 745 total entries. The URL and comparison slots are unchanged.
    screenshot: null
confidence: medium
---

## Notes

The Family and Series values and the 15-row result count were confirmed in the accessibility snapshot and page DOM. After widening Family, the Family control exposed All and Ryzen only, while the Series control exposed All and the selected Ryzen 9000 Series; other Series options were not present. This tests widening to All, not retention across a sibling family, because no sibling Family choice was offered in this resulting state. No comparison was started.
