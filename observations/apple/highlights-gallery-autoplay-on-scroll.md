---
record_type: observation
site: Apple
page: iPhone 18 Pro page Highlights Gallery
context: The iPhone 18 Pro page is at the top; the Highlights Gallery is below the viewport with Play Highlights Gallery shown and Camera selected.
trigger: the Highlights Gallery enters the viewport during page scrolling
action: Scroll down until the Highlights Gallery is visible; do not activate Play Highlights Gallery.
response:
  - The control changes from Play Highlights Gallery to Pause Highlights Gallery without a user click on the control.
  - The Camera highlight is initially selected, then the gallery automatically advances to Colors and later A20 Pro chip.
  - The page URL remains unchanged.
state: The gallery changes from a Play-ready state at page top to automatic slide progression while visible.
intent: continue down the product page
purpose: "hypothesis — automatically present highlights as visitors reach the section while exposing a pause control"
evidence:
  - evidence_class: observed
    url: https://www.apple.com/iphone-18-pro/
    page_title: iPhone 18 Pro and iPhone 18 Pro Max - Apple
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Reload the page and return to scrollY 0; confirm Play Highlights Gallery and Camera are selected. Press PageDown once and confirm Play remains; press PageDown again until the gallery is visible, without clicking the gallery control.
    before: At scrollY 0, Play Highlights Gallery is shown and Camera is selected; after one PageDown the gallery still shows Play.
    after: After the gallery enters view, the control shows Pause; the selected highlight advances from Camera to Colors and then A20 Pro chip without manual activation.
    screenshot: null
confidence: medium
---

## Notes

The in-view auto-start and progression reproduced after a page reload. The exact viewport threshold and behavior under reduced-motion settings were not tested.
