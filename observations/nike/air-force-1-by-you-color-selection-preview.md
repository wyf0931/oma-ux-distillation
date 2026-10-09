---
record_type: observation
site: Nike
page: Nike By You customizer
context: "The Product customization tool is open on a Nike Air Force 1 Low By You design. Vamp / Quarter is the first of ten customizable areas and University Red is selected. The shoe is shown in a 3D preview."
trigger: "The visitor chooses a color for the currently selected shoe area."
action: "Select Black for Vamp / Quarter."
response:
  - "Black becomes the selected color option."
  - "The 3D shoe preview updates to show the Vamp / Quarter in black."
  - "The displayed product price remains $140."
  - "The customization tool stays on Vamp / Quarter, step 1 of 10, and the URL remains on the Builder state."
state: "Vamp / Quarter changes from University Red to Black; the 3D preview and selected swatch update without changing the part, step, price, or URL."
intent: "Preview a different color on the current part of the custom shoe."
purpose: "hypothesis — show the visual effect of a custom choice before the visitor continues designing or buying."
evidence:
  - evidence_class: observed
    url: https://www.nike.com/u/custom-nike-air-force-1-low-by-you-shoes-10002304/2255384254#Builder
    page_title: "Nike Air Force 1 Low By You Custom Men's Shoes. Nike.com"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the public Nike Air Force 1 Low By You product page, activate Customize, dismiss the introductory What's New dialog with Skip, and select Black for Vamp / Quarter."
    before: "The customizer shows a 3D shoe, University Red selected for Vamp / Quarter, step 1 of 10, and a $140 price."
    after: "Black is selected and the 3D shoe preview shows the black Vamp / Quarter. The step, URL, and $140 price remain unchanged. The screenshot captures the resulting preview. No size was selected, and Done, Sign In to Buy, and purchase controls were not activated."
    screenshot: air-force-1-by-you-color-selection-preview.png
confidence: high
---

## Notes

The configurator's price and customizer state are capture-time UI values. This records a reversible visual edit only; the design was not saved, shared, or purchased.
