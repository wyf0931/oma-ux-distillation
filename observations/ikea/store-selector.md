---
site: IKEA
page: Global homepage, store selector
observed_at: 2026-10-08
viewport: unknown
browser: Google Chrome through connected computer-use browser
tool: getApp accessibility state + click
evidence_class: observed
---

# Store selector exposes region and language choices

## Context

URL: https://www.ikea.com/. The homepage initially showed a button labeled `Selected store: IKEA dot s g. To choose another store, open the accordion and use the search tool`.

## Interaction

```yaml
trigger: explicit navigation control
user_intent: choose a regional IKEA store
user_action: activate the selected-store control
system_response:
  - a store search combobox appears
  - the page reports seven stores found
  - available options include country / region and language variants
  - IKEA.sg (English) is marked as selected
state_change: store selector changes from closed to an open list
feedback: selected store is identified and alternative options are listed
animation: unknown
purpose_hypothesis: let visitors switch the regional site without leaving the global homepage
```

## Evidence

- Reproduction: open https://www.ikea.com/ and activate the Selected store control. A cookie notice appeared during the interaction; after choosing Reject, the store selector contents were readable.
- Result: the accessibility state showed a Find online store combobox and seven store/language choices, with IKEA.sg (English) selected.
- Screenshot: not captured.
- Notes / limits: no other store was selected, so destination and persistence behavior were not tested. This does not verify the separate designer-story carousel controls.
