---
record_type: observation
site: Figma
page: Homepage community resources carousel — mobile emulation
context: The Explore what you can do in Figma carousel is visible in a 390x844 CSS-pixel viewport; the carousel reports Slide 1 of 10 and the UI kits card is first.
trigger: touch interaction on the visible carousel content
action: Swipe left across the first carousel card.
response:
  - Touchstart, touchmove, and touchend events reach the card image.
  - The carousel status changes from Slide 1 of 10 to Slide 2 of 10.
  - The page URL remains unchanged.
state: The active carousel position advances from 1 to 2 under a mobile-emulated touch gesture.
intent: browse the next community resource without using the navigation buttons
purpose: "hypothesis — allow mobile visitors to advance the resource set with a touch gesture"
evidence:
  - evidence_class: observed
    url: https://www.figma.com/
    page_title: "Figma: The collaborative canvas for design, code, and AI"
    viewport: 390x844 CSS pixels; deviceScaleFactor 3; mobile emulation
    browser: Chrome for Testing 151.0.7922.34; hasTouch enabled; navigator.maxTouchPoints 1
    captured_at: "2026-10-08"
    tool: Playwright CLI 0.1.22 via Chrome DevTools Protocol touch events
    reproduction: In a temporary mobile-emulated browser context, open the homepage, scroll Explore what you can do in Figma into view, and swipe left across the first UI kits card from approximately x=317 to x=80 at y=764. Reject optional cookies if prompted.
    before: The section reports Slide 1 of 10 and the UI kits card is at the first position.
    after: The section reports Slide 2 of 10; the URL remains https://www.figma.com/.
    screenshot: null
confidence: high
---

## Notes

The event trace confirmed touch events reached the carousel image. This is a mobile-emulated desktop browser result; behavior on a physical device was not tested.
