---
site: Nike
page: Singapore homepage, hero carousel
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Next advances the homepage hero carousel

## Context

URL: https://www.nike.com/sg/. The hero carousel had five slides, a `Pause carousel autoplay` button, Previous and Next buttons, and direct `Go to slide N of 5` controls. At capture, slide 3 of 5 was current.

## Interaction

```yaml
trigger: explicit navigation
user_intent: view another homepage feature
user_action: click Next
system_response:
  - the current slide advances from 3 to 4 of 5
state_change: current slide changes to slide 4
feedback: current-slide control changes to identify slide 4
animation: unknown
purpose_hypothesis: let visitors browse featured campaigns without leaving the homepage
```

## Evidence

- Reproduction: open the URL; note `Current slide, Go to slide 3 of 5`; click Next.
- Result: the immediate post-click snapshot identified slide 4 as current. A later snapshot identified slide 5, so the carousel was still advancing on its own; see `homepage-hero-autoplay.md`.
- Screenshot: not captured.
- Notes / limits: the fifth slide appeared in a later snapshot, not as the immediate click response. Purpose remains a hypothesis.
