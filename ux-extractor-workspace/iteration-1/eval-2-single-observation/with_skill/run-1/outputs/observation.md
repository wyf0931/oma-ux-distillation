---
record_type: observation
site: IKEA
page: IKEA US Sofas & sectionals category listing
context: "The public sofas and sectionals listing loaded with the price filter PRICE_0_50000 active. The page showed 33 items. In the Color facet, the enabled option was labeled ‘red (1)’. The public header showed ‘Hej! Log in or sign up’."
trigger: The enabled Color option labeled “red (1)” was visible on the filtered listing.
action: Click the enabled Color “red (1)” option once.
response:
  - The visible result count changed from 33 items to 1 items.
  - The “red (1)” button became pressed.
  - The URL added the color filter f-colors:10124 while retaining the price filter.
state: "Before: 33 items; price filter active; Red (1) available and unselected. After: 1 item; price and Red filters active; Red option pressed."
intent: Narrow the sofa listing to red items.
purpose: "Hypothesis: let visitors refine the listing by color while seeing the matching result count."
evidence:
  - evidence_class: observed
    url: "https://www.ikea.com/us/en/cat/sofas-sectionals-fu003/?filters=f-price-buckets%3APRICE_0_50000"
    page_title: "Sofas & Couches - Modern & Affordable - IKEA"
    viewport: 1280x720
    browser: "Chrome 154 (headless)"
    section: Sort and Filter; Color
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "Open the source URL in a fresh browser context; confirm the public header displays ‘Hej! Log in or sign up’; capture the initial listing; click the enabled Color ‘red (1)’ button once; capture the resulting listing."
    before: "Status showed 33 items. Under Color, the enabled button ‘red (1)’ was unselected."
    after: "Status showed 1 items. The ‘red (1)’ button was pressed. The URL became https://www.ikea.com/us/en/cat/sofas-sectionals-fu003/?filters=f-colors%3A10124%2Cf-price-buckets%3APRICE_0_50000."
    screenshot: null
confidence: high
---

## Notes

One click was performed as requested. No product was opened and no other control was tested. The result count, pressed state, and updated URL were visible after the click; no repeat was performed.
