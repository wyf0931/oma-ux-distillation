---
site: IKEA
page: Global homepage, store selector search
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + fill + evaluate_script
evidence_class: observed
---

# Store search filters regional site options

## Context

URL: https://www.ikea.com/. The Selected store control was open, with a Find online store combobox and seven store/language options.

## Interaction

```yaml
trigger: text entry
user_intent: find the IKEA site for a region
user_action: type "Malaysia" in the store search combobox
system_response:
  - the live result count changes from seven stores to two
  - the list is reduced to IKEA.my in English and Bahasa Melayu
state_change: the store option set is filtered by the typed query
feedback: the live store count and option list update
animation: unknown
purpose_hypothesis: help visitors find the correct country/language storefront
```

## Evidence

- Reproduction: open the URL, expand the Selected store control, and enter `Malaysia` in the store search field.
- Result: the accessibility status changed from `7 stores found` to `2 stores found`; DOM inspection showed IKEA.my (English) and IKEA.my (Bahasa Melayu).
- Screenshot: not captured.
- Notes / limits: no store option was selected, so route and persistence behavior were not tested.
