---
record_type: observation
site: Amazon
page: Wireless headphone results with Noise Control and Connectivity facets
context: The wireless-headphone query and $5,800 minimum price are active. Active Noise Cancellation and Sound Isolation are selected in Noise Control; 6 results are shown.
trigger: a Connectivity facet is available beside the visible results
action: Select Bluetooth while keeping both Noise Control values selected.
response:
  - The URL retains the query, price, and both Noise Control values, then adds Bluetooth under a separate facet parameter.
  - The result heading changes from 6 results to 2 results.
  - The page header identifies Bluetooth and the combined Noise Control values.
state: Six results with two Noise Control alternatives → two results with those alternatives and Bluetooth selected.
intent: narrow the alternatives to Bluetooth headphones
purpose: "hypothesis — combine a separate connectivity constraint with the selected Noise Control alternatives"
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/s?k=wireless+headphones&rh=p_36%3A580000-%2Cp_n_g-1003195531111%3A23746030011%257C23746032011%2Cp_n_feature_two_browse-bin%3A212335655011&s=price-asc-rank&dc&qid=1791487031&rnid=212335649011&ref=sr_nr_p_n_feature_two_browse-bin_1&ds=v1%3AaOHE2nREWt4RRUAuPYj1bGUWXhvX1F3NAIjs3pT7C%2Bc
    page_title: "Amazon.com: Wireless Headphones - $5,800 & Above / Bluetooth / Active Noise Cancellation Or Sound Isolation"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Starting from the wireless-headphone results with minimum price $5,800 and both Active Noise Cancellation and Sound Isolation selected, select Bluetooth under Connectivity. Inspect the URL, selected refinements, and result heading.
    before: The query and price constraint are active with both Noise Control alternatives selected; the result heading reports 6 results.
    after: Bluetooth is added under Connectivity while the Noise Control values remain in the URL; the heading reports 2 results.
    screenshot: null
confidence: medium
---

## Notes

This interaction did not produce a zero-result state. It shows that the independent Connectivity choice reduced the result set while the selected Noise Control alternatives remained active. No result was opened.
