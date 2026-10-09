---
record_type: page_map
site: Apple
page: MacBook Pro 14-inch purchase configurator
visible_structure:
  - "A model-size selector shows 14-inch selected and 16-inch as another model choice."
  - "An Enter Delivery ZIP field is marked required."
  - "Color options include Space Black and Silver."
  - "Display options for Standard and Nano-texture are present but disabled."
  - "Chip options include M5, M5 Pro, and M5 Max but are disabled."
  - "Unified Memory and SSD Storage sections describe ranges relative to the current chip selection."
  - "Payment, AppleCare, and Continue controls are present lower on the page; several are disabled."
interaction_candidates:
  - "After a permitted delivery ZIP is available, does changing Chip update the available Unified Memory and SSD Storage values?"
  - "Does changing the selected model size alter the available chip or display options?"
  - "Does selecting a color update the product image while preserving the current configuration step?"
limits:
  - "The delivery ZIP field was empty while the display and chip options were disabled; whether a ZIP enables those options was not tested."
  - "No purchase, payment, AppleCare, or Continue action was activated."
  - "This page map did not establish how dependent options change; Chip and Display controls remained disabled during the color-selection follow-up."
related_observations:
  - ../../observations/apple/macbook-pro-color-selection-updates-preview.md
  - ../../observations/apple/macbook-pro-model-size-selection-updates-preview.md
evidence:
  - evidence_class: page-evidence
    url: https://www.apple.com/shop/buy-mac/macbook-pro/14-inch
    page_title: "Buy MacBook Pro, 14-inch - Apple"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
---

## Notes

The public configurator displayed product choices but required a delivery ZIP to enable important configuration controls. No ZIP or other personal details were entered. Use this as a research target only if a future session has an authorized non-personal test location; until then, treat all dependent-option behavior as unobserved.
