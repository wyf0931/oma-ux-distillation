---
record_type: observation
site: Netflix
page: Tudum homepage
context: "The Fan Favorites carousel displays its first group of featured title cards, including Monster: The Lizzie Borden Story, East of Eden, UNABOMBER, and The Gentlemen. The first of four position indicators is active."
trigger: "The visitor requests another group of featured titles."
action: "Click Next items in the Fan Favorites carousel."
response:
  - "The visible cards advance to the next group, including The Whisper Man, The Perfect Lie, Wonka's The Golden Ticket, and Crew Girl."
  - "A Previous items control appears."
  - "The position indicator advances from the first to the second of four positions."
  - "The URL remains https://www.netflix.com/tudum."
state: "Fan Favorites advances from page 1 to page 2 of a four-position sequence without navigating away."
intent: "Browse another group of featured Netflix titles."
purpose: "hypothesis — expose more content in the same homepage region without expanding the whole collection at once."
evidence:
  - evidence_class: observed
    url: https://www.netflix.com/tudum
    page_title: "Netflix Tudum - Go behind the streams"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open Netflix Tudum in an isolated logged-out context and click Next items in Fan Favorites. Click Previous items once to verify the first position, then Next items again to reproduce the second position."
    before: "The first four visible cards are Monster: The Lizzie Borden Story, East of Eden, UNABOMBER, and The Gentlemen; the first of four indicators is active and no Previous items control is shown."
    after: "The visible cards are The Whisper Man, The Perfect Lie, Wonka's The Golden Ticket, and Crew Girl; the second of four indicators is active and Previous items is available. The URL remains unchanged."
    screenshot: fan-favorites-page-2.png
confidence: high
---

## Notes

The two captured viewport states are [page 1](fan-favorites-page-1.png) and [page 2](fan-favorites-page-2.png). This records carousel navigation only; no title was opened or played.
