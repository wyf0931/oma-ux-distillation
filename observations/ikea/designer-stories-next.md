---
site: IKEA
page: Global homepage, Designer stories carousel
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Next advances the Designer stories carousel

## Context

URL: https://www.ikea.com/. The `Designer stories` section exposed nine story cards and Previous / Next controls. At the start of the interaction, Previous was disabled and Next was enabled.

## Interaction

```yaml
trigger: explicit carousel navigation
user_intent: browse more designer stories
user_action: click Next
system_response:
  - Previous changes from disabled to enabled
  - the carousel enters an advanced position
state_change: carousel is no longer at its initial position
feedback: Previous becomes available after advancing
animation: track movement was not measured
purpose_hypothesis: let visitors browse a long sequence of designer stories in place
```

## Evidence

- Reproduction: open the URL, locate `Designer stories`, confirm Previous is disabled and Next is enabled, then click Next.
- Result: the post-action snapshot showed Previous enabled while Next remained available.
- Screenshot: not captured.
- Notes / limits: the active card labels were not captured before/after as a pair; only the carousel boundary state was verified.
