---
site: Netflix
page: Singapore landing page, FAQ
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP, isolated context ux-netflix
tool: take_snapshot + click
evidence_class: observed
---

# Pricing FAQ expands an inline answer

## Context

URL: https://www.netflix.com/sg-zh/. The landing page listed expandable FAQ questions, including `Netflix 如何收费？` (How does Netflix charge?).

## Interaction

```yaml
trigger: explicit disclosure
user_intent: understand subscription pricing
user_action: open Netflix 如何收费？
system_response:
  - the FAQ control enters an expanded state
  - an answer appears inline below it
state_change: answer changes from hidden to visible
feedback: expanded control and associated answer region
animation: unknown
purpose_hypothesis: keep supporting detail available without navigating away from the landing page
```

## Evidence

- Reproduction: open the URL in an isolated context; open `Netflix 如何收费？`.
- Result: the snapshot showed the question expanded and an answer stating that a fixed monthly fee applies, with plans from $15.98 to $29.98.
- Screenshot: not captured.
- Notes / limits: this capture tested only one FAQ item. A follow-up observation tested opening a second question and found that the previously open answer closed ([single-open behavior](faq-single-open.md)).
