---
site: Apple
page: iPhone overview, hero gallery
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Pause control returns the hero gallery to a play state

## Context

URL: https://www.apple.com/iphone/. The hero gallery exposed `Play Hero gallery`. After starting the gallery, the control was labeled `Pause Hero gallery`.

## Interaction

```yaml
trigger: explicit media control
user_intent: stop the moving hero gallery
user_action: click Pause Hero gallery
system_response:
  - the control changes to Play Hero gallery
state_change: gallery returns to its paused / play-available state
feedback: control label reflects the next action
animation: gallery motion was not independently inspected
purpose_hypothesis: give users control over hero motion
```

## Evidence

- Reproduction: open the URL; click Play Hero gallery; click the resulting Pause Hero gallery control.
- Result: the post-action snapshot showed Play Hero gallery again. The same page's control had changed to Pause Hero gallery after Play was clicked.
- Screenshot: not captured.
- Notes / limits: no video element was exposed in the DOM, so only the control state transition was recorded.
