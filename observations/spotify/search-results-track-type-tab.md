---
record_type: observation
site: Spotify
page: Logged-out Web Player search results
context: "Search results for ‘radiohead’ are open on the All tab, with result-type links for Songs, Artists, Albums, Playlists, Profiles, Podcasts and Shows, and Genres and Moods."
trigger: "A submitted search has multiple result types available."
action: "Select Songs."
response:
  - "The browser navigates to /search/radiohead/tracks."
  - "Songs becomes the selected result type and a table of matching tracks is displayed."
  - "The search field retains ‘radiohead’; the page remains in Spotify search."
state: "The query remains ‘radiohead’ while the result context changes from All to Songs."
intent: "Narrow the results to tracks matching Radiohead."
purpose: "hypothesis — allow visitors to focus a broad query on one content type without re-entering the query."
evidence:
  - evidence_class: observed
    url: https://open.spotify.com/search/radiohead
    page_title: "Spotify – 搜索"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the logged-out Spotify search page for `radiohead` and choose Songs in the result-type tabs."
    before: "The search field contains ‘radiohead’; All is the current result type and Songs is an available result-type link."
    after: "The URL changes to /search/radiohead/tracks, Songs is marked selected, a table of tracks appears, and the search field still contains ‘radiohead’. No track is played or opened."
    screenshot: null
confidence: high
---

## Notes

This observes result-type selection only. No playback, library save, or account action was used.
