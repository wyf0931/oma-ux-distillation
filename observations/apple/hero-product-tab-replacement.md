---
site: Apple
page: iPhone overview
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Selecting a hero product tab replaces the hero panel

## Context

URL: https://www.apple.com/iphone/. The hero gallery initially had the `iPhone Duo` tab selected and a tabpanel with that product's heading, short copy, Learn more and Buy links, and product image.

## Interaction

```yaml
trigger: explicit selection
user_intent: view another iPhone model
user_action: select the iPhone 18 Pro tab
system_response:
  - iPhone 18 Pro becomes the selected tab
  - the active tabpanel is replaced with the iPhone 18 Pro heading and copy
  - the product image and Learn more / Buy destinations change to iPhone 18 Pro
state_change: active hero product changes from iPhone Duo to iPhone 18 Pro
feedback: selected tab and matching tabpanel content
animation: unknown
purpose_hypothesis: allow comparison-oriented product exploration without leaving the overview page
```

## Evidence

- Reproduction: load the URL; note the selected `iPhone Duo` tab and its tabpanel; select `iPhone 18 Pro`.
- Result: the post-action snapshot showed the `iPhone 18 Pro` tab selected and the active panel heading, description, image, and CTA links updated.
- Screenshot: not captured.
- Notes / limits: the purpose is a hypothesis. No timing or motion details were measured.
