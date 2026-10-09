---
record_type: observation
site: Airbnb
page: Tokyo homes search results
context: Tokyo results are open with Wi-Fi selected; the Washer quick filter is unchecked.
trigger: an active amenity filter is visible and another quick filter is available
action: Select the Washer quick filter.
response:
  - The Washer checkbox becomes checked while Wi-Fi remains checked.
  - The Filters control reports two applied filters.
  - The URL contains both `amenities[]=4` and `amenities[]=33`.
  - The Tokyo search page remains open and continues to report over 1,000 homes; the count is rounded.
state: The existing Wi-Fi constraint is retained and Washer is added to the active result filters.
intent: restrict the Tokyo listing to homes with both Wi-Fi and a washer
purpose: "hypothesis — let visitors combine amenity constraints while keeping their search context"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/s/%E4%B8%9C%E4%BA%AC--%E4%B8%9C%E4%BA%AC%E9%83%BD--%E6%97%A5%E6%9C%AC/homes?acp_id=d46b2a1c-fa2b-4ec1-a892-89ee2e9a62cf&date_picker_type=calendar&ref_fsid=61e34072-e75c-44d8-b4d3-bc44feb7dfbb&ref_search_session_id=efd3244e-99da-4bb5-a93c-71627cadd6aa&place_id=ChIJXSModoWLGGARILWiCfeu2M0&refinement_paths%5B%5D=%2Fhomes&flexible_trip_lengths%5B%5D=one_week&monthly_start_date=2026-11-01&monthly_length=3&monthly_end_date=2027-02-01&search_mode=regular_search&price_filter_input_type=2&price_filter_num_nights=5&channel=EXPLORE&search_type=filter_change&amenities%5B%5D=4&selected_filter_order%5B%5D=amenities%3A4&update_selected_filters=false
    page_title: 爱彼迎 | 东京 - 度假屋和房源 - 东京都
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Open the recorded Tokyo results with Wi-Fi active. Select Washer from the visible quick filters, then inspect checkbox states, applied-filter count, URL, and result heading after loading settles.
    before: Wi-Fi is checked, Washer is unchecked, and the Filters control reports one applied filter.
    after: Wi-Fi and Washer are both checked; the Filters control reports two applied filters; the URL includes `amenities[]=4` and `amenities[]=33`; the results heading still reports over 1,000 homes.
    screenshot: null
confidence: medium
---

## Notes

The displayed result total is rounded, so the exact effect on listing membership cannot be read from the heading. A direct product listing and two active amenity states were visible after the page settled.
