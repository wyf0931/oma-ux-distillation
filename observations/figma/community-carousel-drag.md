---
record_type: observation
site: Figma
page: Homepage community resources carousel
context: The Explore what you can do in Figma section shows Slide 1 of 10, with the UI kits resource card at the first position.
trigger: pointer interaction on the horizontal community resource carousel
action: Drag the carousel content left from the right side toward the left.
response:
  - The carousel status changes from Slide 1 of 10 to Slide 2 of 10.
  - The page URL remains unchanged.
state: The active carousel position advances from 1 to 2 without leaving the homepage.
intent: browse the next community resource
purpose: "hypothesis — let visitors advance through the resource set by dragging its content"
evidence:
  - evidence_class: observed
    url: https://www.figma.com/
    page_title: "Figma: The collaborative canvas for design, code, and AI"
    viewport: 1512x727
    browser: Chrome for Testing 151.0.7922.34
    captured_at: "2026-10-08"
    tool: Playwright CLI 0.1.22
    reproduction: In a temporary browser context, open the homepage and scroll the Explore what you can do in Figma community carousel into view. Drag horizontally left from x=1200 to x=500 within the carousel row. Reject optional cookies if prompted.
    before: The carousel reports Slide 1 of 10 and the first resource position is active.
    after: The carousel reports Slide 2 of 10; the URL remains https://www.figma.com/.
    screenshot: null
confidence: high
---

## Notes

The drag was performed with a mouse pointer in a desktop viewport. Touch swipe, boundary wrapping, and whether all card content changed are untested; only the active slide count was used to verify advancement.
