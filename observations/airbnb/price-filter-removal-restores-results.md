---
record_type: observation
site: Airbnb
page: Tokyo Homes recovery after zero-result price filter
context: The Tokyo Homes results show no matching homes under the selected price constraint and offer a Remove price filter link.
trigger: the empty filtered state offers a price-filter recovery action
action: Activate Remove price filter.
response:
  - The page returns to Tokyo Homes results and reports more than 1,000 homes; the map reports 20 homes.
  - The URL no longer contains an active `price_max` constraint, while an order-only `selected_filter_order[]=price_max:75` entry remains.
  - The filter control no longer reports an applied-filter count.
state: Zero Tokyo Homes results with price filter → more than 1,000 Tokyo Homes results with price constraint removed.
intent: continue browsing Tokyo homes after the selected price range returns no matches
purpose: "hypothesis — restore a broader listing while preserving destination context"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/s/%E4%B8%9C%E4%BA%AC/homes?ref_fsid=47fc716d-0ebe-4d1b-8387-28fed6177f9d&ref_search_session_id=374af741-6585-4698-a4bd-88f0906792bc&search_mode=regular_search&place_id=ChIJXSModoWLGGARILWiCfeu2M0&refinement_paths%5B%5D=%2Fhomes&flexible_trip_lengths%5B%5D=one_week&monthly_start_date=2026-11-01&monthly_length=3&monthly_end_date=2027-02-01&price_filter_input_type=2&price_filter_num_nights=5&channel=EXPLORE&selected_filter_order%5B%5D=price_max%3A75&search_type=filter_change
    page_title: 爱彼迎 | 东京 - 度假屋和房源 - 东京都
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: From the Tokyo Homes zero-results state, activate Remove price filter and inspect the URL, result heading, map count, and filter control.
    before: The result heading says no homes match the current price constraint; Remove price filter is visible.
    after: The page reports more than 1,000 homes in Tokyo and the map shows 20 homes. The active price_max parameter is absent, though the selected-filter-order entry remains; the filter control has no applied-filter count.
    screenshot: null
confidence: high
---

## Notes

The destination and search mode remain in context. The order-only query parameter remained after the active price constraint was removed; it is not treated as an active filter because the result heading, applied-filter control, and absence of `price_max` all show the broader state.
