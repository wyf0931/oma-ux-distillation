---
record_type: observation
site: Airbnb
page: Tokyo Homes zero-results state after price filter
context: The Tokyo Homes price dialog has a minimum and maximum of 70 SGD, and its availability estimate reports 0%. The apply control still says it will show more than 1,000 homes.
trigger: a price filter with a zero-availability estimate can be applied
action: Apply the selected price filter using the dialog's show-results control.
response:
  - The results URL adds `price_max=75` and a selected-filter-order entry for `price_max:75`; the UI normalizes the entered 70 SGD maximum to 75 SGD.
  - The result heading says no homes fully match the criteria, and advises changing or removing filters or adjusting the search area.
  - The map reports 0 homes and the page offers a Remove price filter link.
state: Tokyo results with over 1,000 homes → no matching homes under the applied price constraint, with a filter-removal recovery path.
intent: inspect the Tokyo Homes matching the selected price range
purpose: "hypothesis — explain an empty filtered state and offer a way to continue"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/s/%E4%B8%9C%E4%BA%AC/homes?ref_fsid=7cf7619e-e13b-4e03-91a8-d68aa259e08e&ref_search_session_id=419679e3-f27e-4ba3-b834-8523d8cdaf2f&place_id=ChIJXSModoWLGGARILWiCfeu2M0&refinement_paths%5B%5D=%2Fhomes&flexible_trip_lengths%5B%5D=one_week&monthly_start_date=2026-11-01&monthly_length=3&monthly_end_date=2027-02-01&search_mode=regular_search&price_filter_input_type=2&price_filter_num_nights=5&channel=EXPLORE&search_type=filter_change&price_max=75&selected_filter_order%5B%5D=price_max%3A75&update_selected_filters=false
    page_title: 爱彼迎 | 东京 - 度假屋和房源 - 东京都
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: In Tokyo Homes results, set the price range to 70–70 SGD until the dialog reports 0% availability, then activate its show-results control. Inspect the final URL, result heading, map count, and recovery controls.
    before: The dialog reports 0% availability for the 70–70 SGD range, while the show-results control still advertises more than 1,000 homes.
    after: The URL contains `price_max=75`; the page says no homes fully match, recommends changing or removing filters or adjusting the area, the map reports 0 homes, and Remove price filter is available.
    screenshot: null
confidence: high
---

## Notes

No listing, account, or booking flow was opened. The UI's price normalization from 70 to 75 SGD and its stale show-results count are preserved as observed; they are not interpreted as separate errors.
