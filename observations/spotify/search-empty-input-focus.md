---
record_type: observation
site: Spotify
page: Logged-out Web Player homepage search
context: The Search control and empty “想播放什么？” (What do you want to play?) combobox are visible; the field is not focused.
trigger: explicit activation of the Search control
action: Activate Search.
response:
  - Focus moves to the empty search combobox.
  - No query-specific suggestions or search-results region appears.
  - The homepage remains visible with its existing Popular Albums and Popular Radio sections.
  - The page URL remains unchanged.
state: The empty search combobox changes from unfocused to focused while the homepage content remains in place.
intent: begin searching for music
purpose: unknown
evidence:
  - evidence_class: observed
    url: https://open.spotify.com/
    page_title: "Spotify - Web Player: Music for everyone"
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open Spotify Web Player logged out and activate the Search button while the query field is empty.
    before: Search is visible; the combobox is empty and unfocused; homepage content is visible.
    after: The empty combobox is focused; no query-specific suggestion region is visible; homepage Popular Albums and Popular Radio remain visible at the same URL.
    screenshot: null
confidence: high
---

## Notes

This logged-out homepage state did not expose the search-specific Quick Links shown by Apple before query entry. It is not evidence about Spotify's logged-in or personalized search experience.
