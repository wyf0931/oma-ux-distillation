---
site: Stripe
page: Singapore homepage, Product navigation
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Product navigation reveals destinations with descriptions

## Context

URL: https://stripe.com/zh-sg. The top navigation exposed a `产品` (Products) button, alongside Solutions, Developers, and Resources.

## Interaction

```yaml
trigger: explicit navigation
user_intent: find a Stripe product area
user_action: click 产品 (Products)
system_response:
  - the button enters an expanded state
  - a product navigation region appears with destinations such as Payments, Managed Payments, Checkout, Billing, Connect, and Radar
  - primary destinations include short descriptions
state_change: product navigation changes from closed to expanded
feedback: destination links and summaries appear
animation: unknown
purpose_hypothesis: help visitors scan the product catalog before navigating
```

## Evidence

- Reproduction: open the URL; click the `产品` button in the header.
- Result: the post-action snapshot showed the button expanded and a navigation region with named product links and descriptions.
- Screenshot: not captured.
- Notes / limits: observed on the `zh-sg` locale. The menu's other subgroups were not explored.
