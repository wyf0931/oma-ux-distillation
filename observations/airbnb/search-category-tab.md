---
site: Airbnb
page: Homepage search category tabs
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Selecting Experiences changes the active search category

## Context

URL: https://zh.airbnb.com/. The homepage search showed tabs for All, Homes, Experiences, and Services. All was selected; Location, Dates, and Guests controls were visible, with Guests showing one guest from a prior local form action.

## Interaction

```yaml
trigger: explicit search mode selection
user_intent: search for an experience rather than all categories
user_action: select the Experiences tab
system_response:
  - Experiences becomes the selected tab
  - Location, Dates, and Guests controls remain visible
  - the Guests summary retains one guest
state_change: active search category changes from All to Experiences
feedback: selected tab state changes
animation: unknown
purpose_hypothesis: let users scope the type of listing before entering search criteria
```

## Evidence

- Reproduction: open the URL; note All selected and the search controls; select Experiences.
- Result: the post-action snapshot marked Experiences selected while the Location, Dates, and Guests controls remained available.
- Screenshot: not captured.
- Notes / limits: no search was submitted and category-specific results were not inspected.
