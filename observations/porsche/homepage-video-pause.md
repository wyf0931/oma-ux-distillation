---
site: Porsche
page: Singapore homepage hero
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Pause control changes the hero video to a play state

## Context

URL: https://www.porsche.com/singapore/en/?cs_redirect=1. After choosing `Only necessary cookies`, the homepage exposed an autoplaying hero video and a button labeled `Pause Video`.

## Interaction

```yaml
trigger: explicit media control
user_intent: stop the hero video
user_action: click Pause Video
system_response:
  - the control label changes to Play Video
state_change: media control moves from pause to play state
feedback: control label reflects the available next action
animation: video playback was not independently measured
purpose_hypothesis: allow users to stop motion in the hero area
```

## Evidence

- Reproduction: open the URL; choose `Only necessary cookies`; click `Pause Video`.
- Result: the post-action snapshot exposed the same control as `Play Video`. A read-only DOM check then reported the hero video as paused at 1.341718 seconds; after approximately three seconds it remained paused at 1.341718 seconds.
- Screenshot: not captured.
- Notes / limits: playback pause was verified for one video and one browser session; resume behavior was not tested.
