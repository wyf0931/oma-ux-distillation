---
record_type: observation
site: Airbnb
page: Tokyo homes search, full-screen map
context: The full-screen Tokyo map shows 20 price-labeled properties; the Wi-Fi filter is active and the Google Maps scale reports 2 km per 47 pixels.
trigger: the map zoom control is visible
action: Activate Zoom in once.
response:
  - The map scale changes from 2 km to 1 km per 47 pixels and the Google Maps zoom URL parameter increases from about 11.53 to 12.53.
  - The map continues to report 20 properties and the Wi-Fi filter remains checked.
  - The Airbnb search URL remains unchanged.
state: The map zoom level increases while the visible search context and active filter remain in place.
intent: inspect property locations at a closer map scale
purpose: "hypothesis — let visitors examine geographic detail without changing their search constraints"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/s/%E4%B8%9C%E4%BA%AC--%E4%B8%9C%E4%BA%AC%E9%83%BD--%E6%97%A5%E6%9C%AC/homes?acp_id=d46b2a1c-fa2b-4ec1-a892-89ee2e9a62cf&date_picker_type=calendar&ref_fsid=61e34072-e75c-44d8-b4d3-bc44feb7dfbb&ref_search_session_id=efd3244e-99da-4bb5-a93c-71627cadd6aa&place_id=ChIJXSModoWLGGARILWiCfeu2M0&refinement_paths%5B%5D=%2Fhomes&flexible_trip_lengths%5B%5D=one_week&monthly_start_date=2026-11-01&monthly_length=3&monthly_end_date=2027-02-01&search_mode=regular_search&price_filter_input_type=2&price_filter_num_nights=5&channel=EXPLORE&search_type=filter_change&amenities%5B%5D=4&selected_filter_order%5B%5D=amenities%3A4&update_selected_filters=false
    page_title: 爱彼迎 | 东京 - 度假屋和房源 - 东京都
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public Tokyo results URL with Wi-Fi active, dismiss the trip-total notice if shown, open the full-screen map, and activate Zoom in once.
    before: The map reports 20 properties; Wi-Fi is checked; the scale reads 2 km per 47 pixels and the linked Google map URL uses z≈11.53.
    after: The map still reports 20 properties and Wi-Fi remains checked; the scale reads 1 km per 47 pixels and the linked Google map URL uses z≈12.53. The Airbnb URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The Zoom in control operated successfully even though individual price-labeled property markers were not interactive through DevTools MCP. No listing was selected or opened.
