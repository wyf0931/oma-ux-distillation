---
record_type: observation
site: Amazon
page: Wireless headphone results with multiple Noise Control values
context: The $5,800 minimum-price and wireless-headphone query remain active. Active Noise Cancellation is selected and the result heading reports 1 result.
trigger: another Noise Control value is available while Active Noise Cancellation remains selected
action: Select Sound Isolation without removing Active Noise Cancellation.
response:
  - The URL retains the query, price constraint, and Active Noise Cancellation value; it adds Sound Isolation in the same facet parameter, separated by an encoded vertical bar.
  - The result heading changes from 1 result to 6 results.
state: One result under Active Noise Cancellation → six results with Active Noise Cancellation and Sound Isolation selected in the same facet group.
intent: include another Noise Control option while keeping the current selection
purpose: "hypothesis — allow multiple alternatives within one filter group"
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/s?k=wireless+headphones&rh=p_36%3A580000-%2Cp_n_g-1003195531111%3A23746030011%257C23746032011&s=price-asc-rank&dc&qid=1791486994&rnid=23746028011&ref=sr_nr_p_n_g-1003195531111_1&ds=v1%3AHZVol92OwD4zlCY%2FWsv2o6bn9sJ9owghCc%2BpGr1DnmA
    page_title: "Amazon.com: Wireless Headphones - $5,800 & Above / Active Noise Cancellation Or Sound Isolat..."
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Starting from the wireless-headphone results with minimum price $5,800 and Active Noise Cancellation selected, select Sound Isolation in Noise Control. Inspect the selected refinements, URL, page title, and result heading.
    before: Active Noise Cancellation is selected; the query and minimum price remain active; the result heading reports 1 result.
    after: Both Noise Control values are selected, the URL joins them with an encoded vertical bar, and the heading reports 6 results.
    screenshot: null
confidence: medium
---

## Notes

Adding the second value increased the result count in this capture. This is consistent with alternative values within one facet group, but the observation establishes only this Amazon session; it does not generalize how other sites combine same-group selections. No result was opened.
