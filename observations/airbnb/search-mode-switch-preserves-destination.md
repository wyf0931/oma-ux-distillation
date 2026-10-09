---
record_type: observation
site: Airbnb
page: Search mode switch from Tokyo Experiences results to Homes results
context: Tokyo Experiences results are open. The compact search summary shows “Tokyo experiences”.
trigger: the current search summary is opened for editing
action: In the expanded search form, select Homes while the Location field still contains Tokyo, then submit Search.
response:
  - The Homes tab becomes selected while the Tokyo location remains in the search form.
  - After submission, the URL path changes from `/experiences` to `/homes` and retains the Tokyo place identifier.
  - The results heading identifies Tokyo and more than 1,000 homes; home listings and the map appear.
state: Tokyo Experiences results → Tokyo Homes results, with the destination retained and the selected result mode changed.
intent: browse homes in the already selected destination instead of experiences
purpose: "hypothesis — let visitors change result type while reusing the current destination"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/s/%E4%B8%9C%E4%BA%AC--%E4%B8%9C%E4%BA%AC%E9%83%BD--%E6%97%A5%E6%9C%AC/homes?search_type=unknown&acp_id=d46b2a1c-fa2b-4ec1-a892-89ee2e9a62cf&date_picker_type=calendar&source=structured_search_input_header&ref_fsid=3a3d70ed-fc49-49d7-a0d6-33ecf7ceea3c&ref_search_session_id=8280d7da-9d0e-4ce8-a326-8067b74d7d26&place_id=ChIJXSModoWLGGARILWiCfeu2M0&refinement_paths%5B%5D=%2Fhomes
    page_title: 爱彼迎 | 东京 - 度假屋和房源 - 东京都
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: From the recorded Tokyo Experiences results, open the compact search control, select the Homes tab while Tokyo remains in Location, activate Search, dismiss the informational trip-total dialog, and inspect the settled URL, results heading, and listing type.
    before: The `/experiences` results are open and the compact search summary reads “Tokyo experiences”. In the expanded form, Experiences is selected and Location is Tokyo.
    after: The `/homes` route is loaded with Tokyo's place identifier. The search header reads Tokyo homes and the heading reports more than 1,000 homes; home listings and a map are visible. No listing was opened.
    screenshot: null
confidence: high
---

## Notes

The result count is rounded. The search flow did not add a user-selected date range; individual result cards display their own dates. No listing, account, or booking flow was opened. An informational trip-total dialog appeared after submission and was dismissed with its acknowledgment button.
