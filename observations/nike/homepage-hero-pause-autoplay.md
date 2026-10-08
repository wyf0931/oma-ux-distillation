---
site: Nike
page: Singapore homepage, hero carousel
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: click + timed snapshot
evidence_class: observed
---

# Pause control stops observed carousel advancement

## Context

URL: https://www.nike.com/sg/. The carousel was on slide 3 of 5 and exposed a button labeled `Pause carousel autoplay`.

## Interaction

```yaml
trigger: explicit control
user_intent: stop automatic slide changes
user_action: click Pause carousel autoplay
system_response:
  - the control label changes to Resume carousel autoplay
  - the current slide remains 3 of 5 over the following 4 seconds
state_change: autoplay enters a paused state
feedback: control label and stable current-slide state
animation: unknown
purpose_hypothesis: give users control over automatic motion and reading time
```

## Evidence

- Reproduction: with slide 3 current, click `Pause carousel autoplay`; inspect the control and current slide, wait approximately 4 seconds, and inspect again.
- Result: the button changed to `Resume carousel autoplay`; two snapshots about four seconds apart continued to identify slide 3 as current.
- Screenshot: not captured.
- Notes / limits: one paused interval was checked. Keyboard, reduced-motion, and touch behavior were not tested.
