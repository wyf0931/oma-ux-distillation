---
site: Vercel
page: Homepage, Products navigation
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Products menu reveals grouped platform destinations

## Context

URL: https://vercel.com/. The global navigation exposed Products, Resources, and Pricing.

## Interaction

```yaml
trigger: explicit navigation
user_intent: discover Vercel platform capabilities
user_action: click Products
system_response:
  - the Products button enters an expanded state
  - links appear under Agent Stack, including AI SDK, AI Gateway, Sandbox, Passport, Connect, and eve
  - links appear under Core Platform, including Security, Content Delivery, Fluid Compute, Observability, and Workflows
state_change: product navigation changes from closed to expanded
feedback: grouped destination links appear
animation: unknown
purpose_hypothesis: help visitors scan the platform's product areas before navigating
```

## Evidence

- Reproduction: open the URL and activate Products in the global navigation.
- Result: the post-action snapshot showed Products expanded and grouped destinations under Agent Stack and Core Platform.
- Screenshot: not captured.
- Notes / limits: only the opening state was inspected; destination links were not followed.
