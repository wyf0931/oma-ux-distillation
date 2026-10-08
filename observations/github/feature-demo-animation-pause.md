---
site: GitHub
page: Logged-out homepage, GitHub features section
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP, isolated context ux-github-motion
tool: take_snapshot + click
evidence_class: observed
---

# Pause control stops the feature-demo animation

## Context

URL: https://github.com/. In the `GitHub features` section, the page described a demonstration animation of Copilot Chat. The control was labeled `Pause` when the page first loaded.

## Interaction

```yaml
trigger: automatic page animation
user_intent: stop the moving demonstration
user_action: click Pause
system_response:
  - the control changes to Play
state_change: the demo animation changes from playing to paused
feedback: control label reflects the available next action
animation: the demo animation was identified by the adjacent accessible description
purpose_hypothesis: let the visitor control motion while reading the product demonstration
```

## Evidence

- Reproduction: open the URL in an isolated logged-out context; locate `GitHub features`; click the `Pause` button beside its demo animation.
- Result: the post-action snapshot showed the same control as `Play`.
- Screenshot: not captured.
- Notes / limits: the animation's frame or playback position was not independently inspected; only the control-state change was verified.
