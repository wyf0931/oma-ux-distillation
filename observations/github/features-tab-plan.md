---
site: GitHub
page: Logged-out homepage, GitHub features section
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP, isolated context ux-github
tool: take_snapshot + click
evidence_class: observed
---

# Selecting Plan replaces the feature summary

## Context

URL: https://github.com/. The `GitHub features` section exposed five tabs: Code, Plan, Collaborate, Automate, and Secure. Code was the initial featured category.

## Interaction

```yaml
trigger: explicit selection
user_intent: inspect the planning capability
user_action: select Plan
system_response:
  - Plan becomes the selected tab
  - the accompanying description changes to explain roadmaps, everyday task tracking, and insights
state_change: selected feature category changes to Plan
feedback: selected tab and live description update
animation: unknown
purpose_hypothesis: summarize multiple product capabilities in one stable page region
```

## Evidence

- Reproduction: open the URL in an isolated context; locate `GitHub features`; select Plan.
- Result: the snapshot marked Plan selected and exposed the copy `Align your team from idea to launch with tools that track work, visualize roadmaps, and gather insights.`
- Screenshot: not captured.
- Notes / limits: only the Plan state was tested; other tabs and reduced-motion behavior were not tested.
