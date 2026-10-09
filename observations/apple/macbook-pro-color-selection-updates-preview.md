---
record_type: observation
site: Apple
page: MacBook Pro 14-inch purchase configurator
context: The public configurator has the 14-inch model selected. Space Black is selected under Color; Display and Chip choices remain disabled while the required delivery ZIP field is empty.
trigger: the enabled Color options are visible in the product configurator
action: Select Silver after Space Black is selected.
response:
  - The selected color label changes from Space Black to Silver.
  - The product preview changes from a dark Space Black MacBook to a silver MacBook.
  - The 14-inch model remains selected and the displayed starting price and lease estimate remain unchanged.
state: 14-inch MacBook Pro in Space Black → 14-inch MacBook Pro in Silver; other selections and displayed price remain unchanged.
intent: preview the MacBook Pro in Silver
purpose: "hypothesis — show the physical appearance associated with the selected product color"
evidence:
  - evidence_class: observed
    url: https://www.apple.com/shop/buy-mac/macbook-pro/14-inch
    page_title: Buy MacBook Pro, 14-inch - Apple
    viewport: 2048x1152 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP evaluate_script and take_screenshot
    reproduction: "Open the public MacBook Pro 14-inch configurator. Without entering a delivery ZIP, select Space Black under Color, then select Silver. Compare the selected-color label, product preview, selected model, and displayed starting price."
    before: "14-inch is selected; Space Black is selected; the preview shows a dark MacBook; starting price is $1,999 and the lease estimate is $38.99 per month. Display and Chip choices are disabled."
    after: "14-inch remains selected; Silver is selected; the preview shows a silver MacBook; starting price remains $1,999 and the lease estimate remains $38.99 per month. Display and Chip choices remain disabled."
    screenshot: macbook-pro-color-silver-after.png
confidence: high
boundaries: []
counterexamples: []
---

## Notes

The before and after captures are shown below.

![Space Black preview before selecting Silver](macbook-pro-color-space-black-before.png)

![Silver preview after selecting Silver](macbook-pro-color-silver-after.png)

Only the public color selector was used. No delivery ZIP, account details, payment information, or purchase action was entered. The preview change is directly visible; dependent chip and display configuration remain untested because those controls were disabled.
