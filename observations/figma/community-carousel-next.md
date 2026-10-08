---
site: Figma
page: Homepage, community resources carousel
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Next changes the active community resource

## Context

URL: https://www.figma.com/. In the region `Explore what you can do in Figma`, the carousel showed one active item at a time, a live slide count, Previous and Next buttons, and a link to browse all templates.

## Interaction

```yaml
trigger: explicit navigation
user_intent: browse community resources
user_action: click Next
system_response:
  - the live slide count advances from 2 of 10 to 3 of 10
  - the active card changes from Websites to Social media
  - the image and destination link change with the active card
state_change: active resource changes from slide 2 to slide 3
feedback: live slide count and card content update
animation: unknown
purpose_hypothesis: let visitors browse examples by resource type in place
```

## Evidence

- Reproduction: open the URL; after the homepage loads, locate `Explore what you can do in Figma`; observe slide 2, then click Next.
- Result: the first post-click snapshot reported Slide 3 of 10; the following snapshot showed the Social media image, heading, and link.
- Screenshot: not captured.
- Notes / limits: the region appeared below the initial homepage section. Load delay and any automatic motion were not measured.
