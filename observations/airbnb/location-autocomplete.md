---
site: Airbnb
page: Homepage search, Location field
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + fill
evidence_class: observed
---

# Location field offers matching places while typing

## Context

URL: https://zh.airbnb.com/. The homepage search had Location, Dates, and Guests controls. The Dates field contained October 9–10, 2026 from a prior local form interaction; the search had not been submitted.

## Interaction

```yaml
trigger: text entry
user_intent: choose a destination
user_action: type "Tokyo" in Location
system_response:
  - the combobox shows the entered query
  - a Search Suggestions listbox appears
  - suggestions include Tokyo, Tokyo Station, Ueno, and Shinjuku
state_change: empty location field changes to a query with place suggestions
feedback: selectable place options appear below the field
animation: unknown
purpose_hypothesis: help users choose a recognized destination before submitting the trip search
```

## Evidence

- Reproduction: open the URL; enter `Tokyo` in the Location field; do not select a suggestion or submit.
- Result: the snapshot showed five place options, including Tokyo, Tokyo, Japan; Tokyo, Japan; Shinjuku, Tokyo, Japan; Tokyo Station; and Ueno.
- Screenshot: not captured.
- Notes / limits: the selected date range was unrelated to this search-field interaction; no location was selected.
