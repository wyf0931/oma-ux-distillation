---
record_type: observation
site: Airbnb
page: Tokyo Homes price filter dialog
context: Tokyo Homes results show over 1,000 homes. The price filter dialog has a minimum price of 70 SGD and a maximum price of 2,300 SGD.
trigger: the price range control is open and its maximum can be edited
action: Replace the maximum price with 70 SGD, matching the current minimum.
response:
  - The minimum and maximum price fields both display 70 SGD.
  - The dialog reports that 0% of homes are available in the selected price range.
  - The page URL and underlying result heading remain unchanged; the dialog has not been applied.
state: Price range 70–2,300 SGD with over 1,000 Tokyo results → 70–70 SGD estimate with 0% available, while results remain unapplied.
intent: restrict the Tokyo search to a low trip-price range
purpose: "hypothesis — preview availability before applying a price constraint"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/s/%E4%B8%9C%E4%BA%AC/homes?place_id=ChIJXSModoWLGGARILWiCfeu2M0&refinement_paths%5B%5D=%2Fhomes&search_type=HOMEPAGE_CAROUSEL_CLICK
    page_title: 爱彼迎 | 东京 - 度假屋和房源 - 东京都
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Open the public Tokyo Homes search, open Filters, select the maximum-price field, replace its value with 70 while the minimum is 70, and inspect the availability estimate before applying.
    before: The price dialog shows a minimum of 70 SGD, a maximum of 2,300 SGD, and over 1,000 homes in the underlying search.
    after: Both price fields show 70 SGD; the dialog reports 0% availability. The underlying URL and result heading remain unchanged because the filter has not been applied.
    screenshot: null
confidence: medium
---

## Notes

The price selection was reversible and no listing was opened. The dialog predicts 0% availability, but the result set is not yet updated; the next observation records applying the filter.
