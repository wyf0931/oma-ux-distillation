---
record_type: observation
site: Porsche
page: Taycan configurator
context: "The Taycan configurator starts with White selected in the $0 Contrasts color group and a vehicle preview."
trigger: "The visitor changes the exterior color option."
action: "Select Black in the Contrasts color group."
response:
  - "Black becomes the selected color option."
  - "The vehicle preview shows the Taycan in black."
  - "The configurator URL adds an options parameter representing the current build."
  - "The displayed MSRP remains $114,250 and the monthly payment estimate remains $1,664.63/mo."
state: "Exterior color changes from White to Black; the preview and selected build state update while the displayed total and monthly estimate remain unchanged."
intent: "Preview the Taycan in another available exterior color."
purpose: "hypothesis — let visitors see a configuration choice on the vehicle before committing to further steps."
evidence:
  - evidence_class: observed
    url: https://configurator.porsche.com/en-US/mode/model/Y1AAI1
    page_title: "Taycan | Porsche Car Configurator (United States)"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "From the Porsche USA model overview, open Configure Taycan. In Exterior Colors > Contrasts, change the selected option from White to Black."
    before: "White is selected at $0. The preview shows the default white Taycan. The configurator displays $114,250 and a $1,664.63/mo estimate."
    after: "Black is selected at $0 and the preview shows a black Taycan. The URL includes an options parameter; displayed MSRP and monthly estimate are unchanged. The after-state screenshot is taycan-configurator-black-selected.png. No build was saved and no dealer or test-drive flow was entered."
    screenshot: taycan-configurator-black-selected.png
confidence: high
---

## Notes

This records a reversible color selection in the public configurator. Pricing and payment values are capture-time UI state, not stable product facts. The selected options are encoded in the URL, but no save or share action was used.
