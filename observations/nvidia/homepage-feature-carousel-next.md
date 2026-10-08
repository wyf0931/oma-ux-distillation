---
site: NVIDIA
page: Regional homepage, primary feature carousel
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Next advances the primary feature story

## Context

URL: https://www.nvidia.com/en-sg/. The primary feature carousel initially showed `Slide 1 of 6`, titled `Cybersecurity — Introducing NVIDIA Open Agent Safety Platform`; its tab was selected.

## Interaction

```yaml
trigger: explicit navigation
user_intent: inspect another featured story
user_action: click Next
system_response:
  - the panel advances to Slide 2 of 6
  - the selected tab changes to the Pinterest / Creatives story
  - the panel heading and associated content change
state_change: active story changes from Cybersecurity to Creatives
feedback: selected tab and active story panel
animation: unknown
purpose_hypothesis: expose multiple current stories in a compact homepage feature area
```

## Evidence

- Reproduction: open the URL; confirm the Cybersecurity story and Slide 1 of 6; click the primary carousel's Next control.
- Result: the post-action snapshot showed `Slide 2 of 6`, the Pinterest story heading, and the Creatives tab selected.
- Screenshot: not captured.
- Notes / limits: the page has several other Next buttons. This action targeted the first carousel's Next button. Purpose remains a hypothesis.
