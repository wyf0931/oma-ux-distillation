---
record_type: observation
site: Airbnb
page: Tokyo homes search results
context: "The Tokyo homes results page has the Wi-Fi filter active, reports more than 1,000 homes, and shows listings alongside an embedded map preview with a Show full-screen map control."
trigger: "The visitor switches from the listing-and-map layout to a map-focused view."
action: "Activate Show full-screen map."
response:
  - "The main results area changes to a full-screen map."
  - "The map reports 20 properties and shows price-labeled listing controls."
  - "The Wi-Fi filter remains checked, and the result heading continues to report more than 1,000 homes."
  - "A Close control appears; the URL remains unchanged."
state: "The split listing/map results layout changes to a map-focused view while the search context and Wi-Fi filter remain active."
intent: "Explore where filtered homes are located."
purpose: "hypothesis — let visitors compare listing locations spatially while preserving their search constraints."
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/s/%E4%B8%9C%E4%BA%AC--%E4%B8%9C%E4%BA%AC%E9%83%BD--%E6%97%A5%E6%9C%AC/homes?acp_id=d46b2a1c-fa2b-4ec1-a892-89ee2e9a62cf&date_picker_type=calendar&ref_fsid=61e34072-e75c-44d8-b4d3-bc44feb7dfbb&ref_search_session_id=efd3244e-99da-4bb5-a93c-71627cadd6aa&place_id=ChIJXSModoWLGGARILWiCfeu2M0&refinement_paths%5B%5D=%2Fhomes&flexible_trip_lengths%5B%5D=one_week&monthly_start_date=2026-11-01&monthly_length=3&monthly_end_date=2027-02-01&search_mode=regular_search&price_filter_input_type=2&price_filter_num_nights=5&channel=EXPLORE&search_type=filter_change&amenities%5B%5D=4&selected_filter_order%5B%5D=amenities%3A4&update_selected_filters=false
    page_title: "爱彼迎 | 东京 - 度假屋和房源 - 东京都"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the previously observed Tokyo homes results URL with Wi-Fi already active, dismiss the trip-total notice with ‘Got it’ if shown, then activate Show full-screen map."
    before: "The page shows the Tokyo results heading, a checked Wi-Fi filter, listing cards, and an embedded map preview indicating 20 homes."
    after: "The results area shows a full-screen Google map with 20 price-labeled listing controls, the Wi-Fi filter remains checked, and the Tokyo results heading and URL are unchanged. A Close control is visible. The screenshot captures the map-focused state."
    screenshot: tokyo-results-fullscreen-map.png
confidence: high
---

## Notes

An attempted follow-up click on a price-labeled map item did not become interactive through Chrome DevTools MCP. No item selection response is claimed or recorded; this does not limit the observed switch to map-focused view.
