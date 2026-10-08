---
site: Mistral AI
page: Homepage, language switcher
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Language switcher opens a short option list

## Context

URL: https://mistral.ai/. The homepage header exposed a Language switcher control.

## Interaction

```yaml
trigger: explicit selection control
user_intent: choose a site language
user_action: activate Language switcher
system_response:
  - the button enters an expanded state
  - a listbox appears with English and Français options
state_change: language list changes from closed to open
feedback: available language buttons become visible
animation: unknown
purpose_hypothesis: let visitors select a supported site language
```

## Evidence

- Reproduction: open the URL; activate Language switcher in the page footer.
- Result: the post-action snapshot showed the button expanded and a listbox containing English and Français.
- Screenshot: not captured.
- Notes / limits: no language option was selected, so navigation and persistence behavior were not tested.
