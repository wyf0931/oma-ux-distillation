---
site: Airbnb
page: Homepage search, Guest selector
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Adding one adult updates the guest summary

## Context

URL: https://zh.airbnb.com/. The homepage search exposed Location, Dates, and Guests controls. Opening Guests showed separate Adult, Child, Infant, and Pet counters; the decrement controls were initially disabled at zero.

## Interaction

```yaml
trigger: explicit form control
user_intent: specify the number of guests
user_action: click Increase adult once
system_response:
  - the summary changes to 1 guest
  - the Adult counter shows 1
  - Decrease adult becomes enabled
state_change: guest count changes from zero to one adult
feedback: updated counter and guest summary
animation: unknown
purpose_hypothesis: let users adjust guest count with bounded per-category controls
```

## Evidence

- Reproduction: open the URL, open Guests, and click Increase adult once. Do not submit the search.
- Result: the post-action snapshot showed `1 adult`, the Guests button summarized `1 guest`, and Decrease adult was enabled.
- Screenshot: not captured.
- Notes / limits: no child, infant, pet, maximum, or search-submission state was tested.
