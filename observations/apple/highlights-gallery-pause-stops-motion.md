---
record_type: observation
site: Apple
page: iPhone 18 Pro page Highlights Gallery
context: The Highlights Gallery is visible and advancing automatically; Pause Highlights Gallery is shown.
trigger: explicit pause request during automatic slide progression
action: Activate Pause Highlights Gallery.
response:
  - The control changes to Play Highlights Gallery.
  - The gallery remains on the Siri AI highlight during a subsequent four-second observation interval.
  - The page URL remains unchanged.
state: The gallery changes from automatic progression to a paused state with Play available.
intent: stop the moving highlights at the current position
purpose: "hypothesis — let visitors control the pace of the automatic highlights sequence"
evidence:
  - evidence_class: observed
    url: https://www.apple.com/iphone-18-pro/
    page_title: iPhone 18 Pro and iPhone 18 Pro Max - Apple
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Scroll until Highlights Gallery shows Pause, then activate Pause Highlights Gallery and inspect the control and selected tab immediately and again after four seconds.
    before: Pause Highlights Gallery is shown; A20 Pro chip is selected.
    after: The control shows Play Highlights Gallery; Siri AI is selected and remains selected over the following four seconds.
    screenshot: null
confidence: medium
---

## Notes

The selected slide advanced from A20 Pro chip to Siri AI around the time the pause action was applied. The stable interval after the control changed to Play supports a paused state, but the exact frame at which pausing took effect is not resolved.
