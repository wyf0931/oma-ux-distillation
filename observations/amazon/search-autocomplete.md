---
site: Amazon
page: US homepage search
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + fill
evidence_class: observed
---

# Search input offers query completions while typing

## Context

URL: https://www.amazon.com/. The header exposed a department selector, a `Search Amazon` searchbox, and a Go button.

## Interaction

```yaml
trigger: text entry
user_intent: find a product
user_action: type "wireless mouse" into Search Amazon
system_response:
  - the searchbox retains the entered query
  - a list of ten query suggestions appears
  - suggestions include product-specific refinements such as brand, device, and use-case terms
state_change: search input changes from empty to a query with suggestions open
feedback: selectable suggestion buttons appear below the search field
animation: unknown
purpose_hypothesis: help refine a query before submitting it
```

## Evidence

- Reproduction: open the URL and fill `wireless mouse` in `Search Amazon`; do not submit.
- Result: the snapshot showed ten suggestion buttons, including `wireless mouse and keyboard`, `wireless mouse logitech`, and `wireless mouse ergonomic`.
- Screenshot: not captured.
- Notes / limits: suggestion ranking and result behavior after selection were not tested. No search was submitted.
