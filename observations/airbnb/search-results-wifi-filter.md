---
record_type: observation
site: Airbnb
page: Tokyo homes search results
context: Tokyo search results show over 1,000 homes; the Filters dialog is open with Wi-Fi unchecked.
trigger: explicit selection and application of an amenity facet
action: Select Wi-Fi, then apply the filter with “显示超过 1000 个房源” (Show over 1,000 homes).
response:
  - The Wi-Fi option becomes checked.
  - The filter dialog closes and the Tokyo results page remains open.
  - The URL gains the `amenities[]=4` refinement parameter.
  - The heading continues to report more than 1,000 homes; the displayed count is rounded.
state: The Tokyo search remains in place with the Wi-Fi amenity filter active.
intent: limit Tokyo homes to listings with Wi-Fi
purpose: "hypothesis — let visitors apply an amenity condition to a broad search result set"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/s/%E4%B8%9C%E4%BA%AC--%E4%B8%9C%E4%BA%AC%E9%83%BD--%E6%97%A5%E6%9C%AC/homes?acp_id=d46b2a1c-fa2b-4ec1-a892-89ee2e9a62cf&date_picker_type=calendar&ref_fsid=61e34072-e75c-44d8-b4d3-bc44feb7dfbb&ref_search_session_id=efd3244e-99da-4bb5-a93c-71627cadd6aa&place_id=ChIJXSModoWLGGARILWiCfeu2M0&refinement_paths%5B%5D=%2Fhomes&flexible_trip_lengths%5B%5D=one_week&monthly_start_date=2026-11-01&monthly_length=3&monthly_end_date=2027-02-01&search_mode=regular_search&price_filter_input_type=2&price_filter_num_nights=5&channel=EXPLORE&search_type=filter_change&amenities%5B%5D=4&selected_filter_order%5B%5D=amenities%3A4&update_selected_filters=false
    page_title: 爱彼迎 | 东京 - 度假屋和房源 - 东京都
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Search for Tokyo homes, open Filters, select Wi-Fi, then activate Show over 1,000 homes.
    before: The Tokyo result page reports over 1,000 homes; the Wi-Fi amenity option is unchecked in Filters.
    after: The URL includes `amenities[]=4`; the Wi-Fi checkbox is checked on the results page, which still reports over 1,000 homes.
    screenshot: null
confidence: medium
---

## Notes

The active filter is verified by the URL and checked state. The result count is rounded, so the exact number of listings removed is unknown.
