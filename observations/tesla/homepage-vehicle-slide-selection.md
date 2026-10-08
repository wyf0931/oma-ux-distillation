---
site: Tesla
page: Homepage, vehicle slide selection
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Selecting a vehicle slide changes the selected tab

## Context

URL: https://www.tesla.com/. A five-item vehicle slide control group exposed tabs named Slide 1 through Slide 5. The first tab was selected; its associated links included Model Y Order Now and Learn More destinations. Slide 2 exposed Model 3 lease, order, and learn-more links.

## Interaction

```yaml
trigger: explicit selection
user_intent: inspect another vehicle option
user_action: select Slide 2
system_response:
  - Slide 2 becomes the selected tab
state_change: selected vehicle slide changes from 1 to 2
feedback: selected tab state
animation: unknown
purpose_hypothesis: move among vehicle offers from the homepage
```

## Evidence

- Reproduction: open the URL; inspect the five-item vehicle slide group; select Slide 2.
- Result: the post-action snapshot showed Slide 2 focused and selected. Its associated links target Model 3 lease, order, and product information.
- Screenshot: not captured.
- Notes / limits: the selected tab state was verified. A matching visible hero heading change was not verified, so no such change is claimed.
