---
record_type: observation
site: Apple
page: MacBook Pro 14-inch purchase configurator
context: The configurator has 14-inch selected and Silver selected. The gallery image description identifies a 14-inch MacBook Pro; Display and Chip choices are disabled while the required delivery ZIP field is empty.
trigger: the 14-inch and 16-inch model choices are enabled in the configurator
action: Select the 16-inch model.
response:
  - The 16-inch model card becomes selected and the 14-inch card is deselected.
  - The gallery image description changes from a 14-inch to a 16-inch MacBook Pro.
  - The purchase summary changes from a $1,999 starting price and $38.99 monthly lease estimate to $2,999 and $57.99; Silver remains selected.
  - The URL stays on `/shop/buy-mac/macbook-pro/14-inch`; Display and Chip choices remain disabled.
state: 14-inch MacBook Pro in Silver, starting at $1,999 → 16-inch MacBook Pro in Silver, starting at $2,999, with the current page URL and unavailable dependent choices unchanged.
intent: compare the 16-inch model configuration
purpose: "hypothesis — reflect the selected model size in the product representation and purchase summary"
evidence:
  - evidence_class: observed
    url: https://www.apple.com/shop/buy-mac/macbook-pro/14-inch
    page_title: Buy MacBook Pro, 14-inch - Apple
    viewport: 2048x1152 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP evaluate_script and take_screenshot
    reproduction: "Open the public MacBook Pro 14-inch configurator with 14-inch and Silver selected. Select 16-inch under Model. Do not enter a delivery ZIP or continue to purchase."
    before: "14-inch and Silver are selected; the gallery image description says 14-inch MacBook Pro; starting price is $1,999 and lease estimate is $38.99 per month."
    after: "16-inch and Silver are selected; the gallery image description says 16-inch MacBook Pro; starting price is $2,999 and lease estimate is $57.99 per month. The URL remains `/shop/buy-mac/macbook-pro/14-inch`; Display and Chip remain disabled."
    screenshot: macbook-pro-16inch-model-selection-after.jpg
  - evidence_class: observed
    url: https://www.apple.com/shop/buy-mac/macbook-pro/14-inch
    page_title: Buy MacBook Pro, 14-inch - Apple
    viewport: 2048x1152 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP evaluate_script and take_screenshot
    reproduction: "With the model set back to 14-inch and Silver, select 16-inch again and compare the selection, gallery image description, purchase summary, and URL."
    before: "14-inch and Silver are selected; the gallery image description says 14-inch MacBook Pro; starting price is $1,999 and lease estimate is $38.99 per month."
    after: "16-inch and Silver are selected; the gallery image description says 16-inch MacBook Pro; starting price is $2,999 and lease estimate is $57.99 per month. The URL remains `/shop/buy-mac/macbook-pro/14-inch`; Display and Chip remain disabled."
    screenshot: macbook-pro-model-16-inch-after.jpg
  - evidence_class: observed
    url: https://www.apple.com/shop/buy-mac/macbook-pro/14-inch
    page_title: Buy MacBook Pro, 14-inch - Apple
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "In an isolated Playwright browser context, confirm 14-inch and Silver are selected, then select 16-inch under Model. Compare the gallery image description, purchase estimates, selected color, and URL."
    before: "14-inch and Silver are selected; the gallery image description says 14-inch MacBook Pro; starting price is $1,999 and lease estimate is $38.99 per month."
    after: "16-inch and Silver are selected; the gallery image description says 16-inch MacBook Pro; starting price is $2,999 and lease estimate is $57.99 per month. The URL remains `/shop/buy-mac/macbook-pro/14-inch`; Display and Chip remain disabled."
    screenshot: macbook-pro-model-16-inch-playwright-after.png
confidence: high
boundaries: []
counterexamples: []
---

## Notes

The 14-to-16-inch model change and its reverse-and-repeat were captured from equivalent selections. The before and after screenshots show the model card, gallery image, and purchase summary. The transition reproduced with Chrome DevTools MCP and an isolated Playwright session. The native size radio is visually hidden, so each browser automation activated its associated label. No ZIP, account information, or purchase action was entered. Dependent Chip and Display choices remained untested because they were disabled.

![14-inch model before selection](macbook-pro-model-14-inch-before.jpg)

![16-inch model after selection](macbook-pro-model-16-inch-after.jpg)

![16-inch model after the Playwright reproduction](macbook-pro-model-16-inch-playwright-after.png)
