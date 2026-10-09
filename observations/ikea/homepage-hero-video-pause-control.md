---
record_type: observation
site: IKEA
page: Global homepage hero video
context: A fresh homepage load is at the top of the page; the muted Xbox hero video is already playing and its control reads Pause video.
trigger: the hero video is playing with an explicit pause control
action: Activate Pause video.
response:
  - The control label changes to Play video.
  - The associated video is paused and remains paused across a two-second observation interval.
  - The page URL remains unchanged.
state: The playing hero video changes to a paused state and exposes a play action.
intent: stop the hero video's motion
purpose: "hypothesis — let visitors stop background motion while keeping a way to resume"
evidence:
  - evidence_class: observed
    url: https://www.ikea.com/
    page_title: Hej! Welcome to IKEA Global
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: In a fresh isolated context, open IKEA's homepage and confirm the top Xbox hero video is already playing with a Pause video control; reject optional cookies if prompted, then activate Pause video. Do not activate other media controls.
    before: Before any media control is activated, the hero video is unpaused at first inspection with currentTime about 11.57 seconds and muted=true; the control reads Pause video. After rejecting optional cookies, it is still playing.
    after: The control reads Play video; the hero video is paused at currentTime 2.53 seconds and remains paused after a two-second wait; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The page was opened in a fresh isolated context with no play action. Playback time changed between the pre-action inspection and the pause check, so exact playhead continuity is not claimed. This is the top Xbox hero video, separate from the lower Pause slideshow control documented in `homepage-slideshow-pause-control.md`.
