---
site: Linear
page: Public homepage product navigation
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP, isolated context ux-research
tool: take_snapshot + click
evidence_class: observed
---

# Product button reveals grouped product destinations

## Context

URL: https://linear.app/. The top navigation exposed Product and Resources buttons. Only the public Product menu was explored.

## Interaction

```yaml
trigger: explicit navigation
user_intent: discover product capabilities
user_action: click Product
system_response:
  - the Product button enters an expanded state
  - links appear for Intake, Plan and monitor, AI and automations, Build, review and ship, and supporting destinations
  - each primary link includes a short description
state_change: product navigation changes from closed to expanded
feedback: visible destination links and expanded button state
animation: unknown
purpose_hypothesis: group product entry points and summarize each destination before navigation
```

## Evidence

- Reproduction: open the URL in an isolated browser context; click Product in the top navigation.
- Result: the button changed to expanded and the menu exposed the named links and short descriptions.
- Screenshot: not captured.
- Notes / limits: only the open-menu state was examined. The embedded product demo elsewhere on the page was not recorded.
