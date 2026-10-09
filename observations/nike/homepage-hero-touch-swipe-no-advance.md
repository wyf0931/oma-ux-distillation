---
record_type: observation
site: Nike
page: Singapore homepage hero carousel — mobile emulation
context: The five-slide Nike homepage hero carousel is at Slide 1 of 5 in a 390x844 CSS-pixel viewport, with carousel autoplay and direct slide controls visible.
trigger: touch interaction on the active hero slide
action: Swipe left across the active slide content.
response:
  - Touchstart, touchmove, and touchend events reach an anchor inside the active slide.
  - The current-slide control remains Slide 1 of 5.
  - The page URL remains unchanged.
state: No carousel position change is observed after the touch-emulated swipe in this session.
intent: view the next hero slide by touch
purpose: unknown
evidence:
  - evidence_class: observed
    url: https://www.nike.com/sg/
    page_title: "Nike. Just Do It. Nike SG"
    viewport: 390x844 CSS pixels; deviceScaleFactor 3; mobile emulation
    browser: Chrome for Testing 151.0.7922.34; hasTouch enabled; navigator.maxTouchPoints 1
    captured_at: "2026-10-08"
    tool: Playwright CLI 0.1.22 via Chrome DevTools Protocol touch events
    reproduction: In a temporary mobile-emulated context, open the homepage and swipe left across the visible hero slide from approximately x=328 to x=62 at y=411. Observe the current-slide control immediately after the gesture.
    before: The current-slide control is Slide 1 of 5; the carousel is at the public homepage URL.
    after: The current-slide control remains Slide 1 of 5 and the URL is unchanged; the touch events reached an anchor inside the active slide.
    screenshot: null
confidence: medium
---

## Notes

This records one mobile-emulated gesture only. It does not establish physical-device behavior or that Nike never supports swipe; the specific gesture did not advance the active slide in this session.
