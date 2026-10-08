---
site: AMD
page: Homepage, AI Portfolio section
observed_at: 2026-10-08
viewport: 1440x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click + evaluate_script
evidence_class: observed
---

# Next advances the AI Portfolio carousel

## Context

URL: https://www.amd.com/en.html. In the `A Comprehensive AI Portfolio` section, the active item was `Data Center AI` (Slide 1 of 5). Its card included a description and links for Instinct GPUs, EPYC CPUs, Pensando DPUs & NICs, and Versal AI Core SOCs.

## Interaction

```yaml
trigger: explicit navigation
user_intent: inspect the next AI portfolio area
user_action: click Next
system_response:
  - the active slide advances to Edge AI (Slide 2 of 5)
  - the card image, description, and product links correspond to Edge AI
state_change: active slide changes from 1 to 2
feedback: active card content changes
animation: unknown
purpose_hypothesis: let visitors browse a bounded set of AI solution areas in place
```

## Evidence

- Reproduction: open the URL and locate `A Comprehensive AI Portfolio`; record `Data Center AI` as active; click its Next button.
- Result: the click succeeded. DOM inspection showed the active slide class on `Slide 2 of 5`, headed `Edge AI`, with its associated copy and links.
- Screenshot: not captured.
- Notes / limits: the purpose is a hypothesis. No timing or motion details were measured.
