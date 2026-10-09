---
record_type: observation
site: Airbnb
page: Tokyo Experiences search results
context: The Experiences search mode is selected, Location contains “东京, 东京都, 日本”, Dates are Any time, and the search has not been submitted.
trigger: a query is ready to submit in a selected search mode
action: Submit the Tokyo search with Experiences selected.
response:
  - The results URL retains the `/experiences` route and the Experiences refinement.
  - The search header identifies the destination as Tokyo experiences.
  - The results page shows Tokyo experience listings with activity type, location, and duration details.
  - The page remains in the Experiences search context; no booking flow opens.
state: The selected Experiences mode scopes the submitted Tokyo search to experience listings.
intent: find experiences available in Tokyo
purpose: "hypothesis — let visitors choose the search result type before entering search criteria"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/s/%E4%B8%9C%E4%BA%AC--%E4%B8%9C%E4%BA%AC%E9%83%BD--%E6%97%A5%E6%9C%AC/experiences?place_id=ChIJXSModoWLGGARILWiCfeu2M0&refinement_paths%5B%5D=%2Fexperiences&location_bb=Qg9FEEML6ztCDhOAQwuQGA%3D%3D&acp_id=d46b2a1c-fa2b-4ec1-a892-89ee2e9a62cf&date_picker_type=calendar&source=structured_search_input_header&search_type=autocomplete_click
    page_title: 东京的缤纷体验|原汁原味的5星体验 - 爱彼迎
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Open the Airbnb homepage in a fresh isolated context. Select the Experiences tab, enter Tokyo in Location and select “东京, 东京都, 日本” from suggestions, then activate Search without entering dates or guests. Inspect the resulting URL, header, and listing results.
    before: The Experiences tab is selected; Location is Tokyo; Dates are Any time; Guests shows Add guests; Search has not been submitted.
    after: The URL path contains `/experiences`; the header says Tokyo experiences; the page lists Tokyo experiences such as food tours, cultural tours, and boat trips with locations and durations. No experience detail or booking flow was opened.
    screenshot: null
confidence: medium
---

## Notes

Selecting the Experiences tab earlier changed the homepage URL to `/experiences` before the Location query was entered. The scoped search then preserved that route through submission. No dates were selected.
