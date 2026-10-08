---
site: Spotify
page: Web Player search
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP, isolated context ux-spotify
tool: take_snapshot + click + fill
evidence_class: observed
---

# Search results update as a query is typed

## Context

URL: https://open.spotify.com/. The logged-out Web Player exposed a Search button in its main navigation and a `想播放什么？` (What do you want to play?) combobox after search was opened.

## Interaction

```yaml
trigger: text entry
user_intent: find an artist or music
user_action: type "Taylor Swift" into the search combobox
system_response:
  - the query remains in the combobox
  - a Popular results region appears with an artist result
  - song results appear with track titles and per-track play / options controls
  - an artist region and related albums/playlists appear below
state_change: home view changes into query-specific search content
feedback: result sections and item controls are labeled in the page
animation: unknown
purpose_hypothesis: support artist, track, and collection discovery from one query
```

## Evidence

- Reproduction: open the Web Player in an isolated context; click Search; fill `Taylor Swift`; do not play a track.
- Result: the snapshot showed Popular results, song search results, an artist result, and related releases for the query.
- Screenshot: not captured.
- Notes / limits: no result was selected and no audio was played. The preview player controls were disabled while logged out.
