---
site: GitHub
page: Logged-out homepage, GitHub features section
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP, isolated context ux-github-motion
tool: take_snapshot + click
evidence_class: observed
---

# Play control resumes the feature-demo animation state

## Context

URL: https://github.com/. In the `GitHub features` section, the demonstration animation was paused and its control was labeled `Play`.

## Interaction

```yaml
trigger: explicit media control
user_intent: resume the product demonstration
user_action: click Play
system_response:
  - the control changes to Pause
state_change: the demo animation changes from paused to playing state
feedback: control label reflects the available next action
animation: individual animation frames were not inspected
purpose_hypothesis: allow users to resume moving content after pausing
```

## Evidence

- Reproduction: open the URL in an isolated logged-out context; in `GitHub features`, click Pause to stop the demo; click the resulting Play control.
- Result: the post-action snapshot showed the control as Pause again.
- Screenshot: not captured.
- Notes / limits: playback time or frame changes were not independently measured.
