---
site: IKEA
page: Global homepage, store selector
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click + evaluate_script
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

- Reproduction: open https://www.ikea.com/ in a fresh page and activate the Selected store control.
- Result: the button entered an expanded state. The page exposed a Find online store combobox and a listbox with seven options: IKEA.sg (English), IKEA.co.id (English and Bahasa Indonesia), IKEA.my (English and Bahasa Melayu), and IKEA.com/th (English and Thai). IKEA.sg (English) was selected.
- Screenshot: not captured.
- Notes / limits: no other store was selected, so destination and persistence behavior were not tested. A separate CUA run showed a cookie notice during the first attempt; this DevTools reproduction was unobstructed. The store state did not change. This does not verify the separate designer-story carousel controls.
