---
site: Airbnb
page: Homepage search
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Date selection guides the user from check-in to check-out

## Context

URL: https://zh.airbnb.com/. After dismissing the informational dialog about displaying trip totals, the homepage search exposed tabs for All, Homes, Experiences, and Services; a Location field; a Dates control; and a Guests control.

## Interaction

```yaml
trigger: explicit form control
user_intent: choose stay dates
user_action:
  - open Dates
  - select October 9, 2026
  - select October 10, 2026
system_response:
  - a calendar opens and marks past dates as unavailable
  - after check-in selection, later available dates are described as checkout choices
  - after checkout selection, the Dates button summarizes October 9–10
state_change: empty date range becomes a one-night selected range
feedback: calendar selection labels and summary in the search control
animation: unknown
purpose_hypothesis: guide a two-step date choice and prevent past dates from being selected
```

## Evidence

- Reproduction: open the URL, dismiss the informational dialog, open Dates, select October 9 and then October 10. Do not submit the search.
- Result: the initial calendar disabled October 1–7 as past dates; October 9 became the selected check-in; later dates were labeled as checkout choices; the control summarized `10月9日 - 10月10日`.
- Screenshot: not captured.
- Notes / limits: the homepage prefilled destination recommendations elsewhere on the page; none were opened or recorded. Dates were selected only in the local form state; search was not submitted.
