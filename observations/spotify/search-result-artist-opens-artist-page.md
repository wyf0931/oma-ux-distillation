---
record_type: observation
site: Spotify
page: Logged-out Web Player, artist search results
context: Search results for “Taylor Swift” are filtered to Artists; the search field contains the query and Taylor Swift appears as an artist result.
trigger: an artist result link is available in the filtered result list
action: Select the Taylor Swift artist result.
response:
  - The browser navigates from `/search/taylor%20swift/artists` to the canonical artist path `/artist/06HL4z0CvFAxyc27GXpf02`.
  - An artist profile page appears with a Taylor Swift heading and sections for popular tracks, artist picks, albums, and playlists.
  - The search field is empty on the artist page; the search query is not retained in the URL.
state: The query-results context changes to an artist profile and the query state is cleared.
intent: open the selected artist's profile
purpose: "hypothesis — let visitors move from a search result to the artist's full catalog"
evidence:
  - evidence_class: observed
    url: https://open.spotify.com/search/taylor%20swift/artists
    page_title: Spotify – 搜索
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open Spotify search results for “Taylor Swift”, select the Artists result type, then open the Taylor Swift artist result. Do not activate playback controls.
    before: The URL is https://open.spotify.com/search/taylor%20swift/artists; Artists is selected, the search field contains “Taylor Swift”, and a Taylor Swift artist result link is visible.
    after: The URL is https://open.spotify.com/artist/06HL4z0CvFAxyc27GXpf02; the page title is Taylor Swift | Spotify, the main heading is Taylor Swift, and the search field is empty. No track is played.
    screenshot: null
confidence: high
---

## Notes

This is result selection and entity navigation, not result-set refinement. The artist page was inspected only for its visible destination context; no content was played, saved, or followed.
