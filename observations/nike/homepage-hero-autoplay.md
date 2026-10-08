---
site: Nike
page: Singapore homepage, hero carousel
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + timed observation
evidence_class: observed
---

# Hero carousel advances while idle

## Context

URL: https://www.nike.com/sg/. The hero carousel exposed five direct slide controls and a button labeled `Pause carousel autoplay`.

## Interaction

```yaml
trigger: elapsed time while page is open
user_intent: unknown
user_action: none during the observation interval
system_response:
  - current slide changes from slide 1 to slide 3 over about 4 seconds
state_change: active slide advances without a user input
feedback: current-slide control identifies each sample state
animation: unknown
purpose_hypothesis: rotate through featured campaigns automatically
```

## Evidence

- Reproduction: observe the current slide control, wait approximately 4 seconds without interacting, then inspect it again.
- Result: one snapshot showed slide 1 current; after approximately 4 seconds without input, a later snapshot showed slide 3 current.
- Screenshot: not captured.
- Notes / limits: the interval is approximate and only one timed sample was taken. This establishes that the observed page advanced while idle, not a stable interval or all device behavior.
