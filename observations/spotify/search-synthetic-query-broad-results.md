---
record_type: observation
site: Spotify
page: Logged-out Web Player search
context: The public homepage is open without an account session; the search combobox is empty and homepage content is visible.
trigger: query text is entered in the search combobox
action: Enter the synthetic query qzvqxjrnzzzztttt998877665544.
response:
  - The browser navigates to the query-specific search URL and the combobox retains the query.
  - The page displays Popular Results and sections for songs, artists, albums, playlists, podcasts, and genres.
  - The visible items do not match the synthetic query text.
  - No no-results message or query recovery options are visible in this state.
state: The homepage changes to a search results page with the synthetic query retained and broad unrelated content displayed.
intent: search for a specific item matching the entered query
purpose: "hypothesis — keep the search page populated with broad content when query-specific matches are unavailable; the result logic was not inspected"
evidence:
  - evidence_class: observed
    url: https://open.spotify.com/search/qzvqxjrnzzzztttt998877665544
    page_title: "Spotify – 搜索"
    viewport: 1512x727
    browser: Chrome 154.0.0.0
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the logged-out homepage in an isolated context and enter the synthetic query in the search combobox; do not log in or select a result.
    before: The search combobox is empty and the homepage shows logged-out content.
    after: The URL and combobox contain the synthetic query; the search page shows broad results that do not match the query, with no explicit no-results message or recovery options.
    screenshot: null
confidence: medium
---

## Notes

This is a single logged-out session. It bounds the observed state only; authenticated, personalized, and other query behavior remains untested.
