---
record_type: observation
site: Airbnb
page: Tokyo homes search results
context: Tokyo results show Wi-Fi and Washer as selected quick filters.
trigger: two amenity filters are active on a result page
action: Clear the Wi-Fi quick filter while Washer remains selected.
response:
  - Wi-Fi becomes unchecked and Washer remains checked.
  - The Filters control reports one applied filter.
  - The URL's `amenities[]` parameter retains `33` for Washer and no longer includes `4` for Wi-Fi.
  - The Tokyo results page remains open and reports over 1,000 homes; the count is rounded.
state: The Wi-Fi constraint is removed independently while the Washer constraint and listing context remain active.
intent: broaden the results by removing Wi-Fi while retaining the washer requirement
purpose: "hypothesis — allow visitors to revise one constraint without clearing the rest of their search"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/s/%E4%B8%9C%E4%BA%AC--%E4%B8%9C%E4%BA%AC%E9%83%BD--%E6%97%A5%E6%9C%AC/homes?acp_id=d46b2a1c-fa2b-4ec1-a892-89ee2e9a62cf&date_picker_type=calendar&ref_fsid=61e34072-e75c-44d8-b4d3-bc44feb7dfbb&ref_search_session_id=efd3244e-99da-4bb5-a93c-71627cadd6aa&place_id=ChIJXSModoWLGGARILWiCfeu2M0&refinement_paths%5B%5D=%2Fhomes&flexible_trip_lengths%5B%5D=one_week&monthly_start_date=2026-11-01&monthly_length=3&monthly_end_date=2027-02-01&search_mode=regular_search&price_filter_input_type=2&price_filter_num_nights=5&channel=EXPLORE&search_type=filter_change&amenities%5B%5D=4&selected_filter_order%5B%5D=amenities%3A4&update_selected_filters=false
    page_title: 爱彼迎 | 东京 - 度假屋和房源 - 东京都
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: On Tokyo search results with Wi-Fi and Washer both active, clear Wi-Fi from the visible quick filters. After the page settles, inspect checkbox states, applied-filter count, URL, and result heading.
    before: Wi-Fi and Washer are checked; the Filters control reports two applied filters.
    after: Wi-Fi is unchecked, Washer remains checked, and the Filters control reports one applied filter. The URL's active `amenities[]` parameter contains `33` only; the Tokyo heading still reports over 1,000 homes.
    screenshot: null
confidence: medium
---

## Notes

The `selected_filter_order[]` portion of the URL still contained entries for both amenities after Wi-Fi was removed, although the active amenity parameter, checkbox states, and applied-filter count showed only Washer as active. This URL detail is recorded without inferring its purpose. The rounded result total does not reveal an exact listing-count change.
