---
record_type: observation
site: IKEA
page: Global homepage, Designer stories carousel
context: The Designer stories carousel is at its initial position and shows the first two cards, David Wahl and Friso Wiersma.
trigger: the Next slide control is enabled while Previous slide is disabled
action: Activate Next slide in the Designer stories carousel.
response:
  - The carousel scroll position changes from 0 to 336 CSS pixels.
  - The two visible cards change from David Wahl and Friso Wiersma to Friso Wiersma and Wiebke Braasch.
  - Previous slide becomes enabled, Next slide remains enabled, and the page URL is unchanged.
state: The visible two-card window advances by one card while the carousel remains on the homepage.
intent: browse the next IKEA designer story
purpose: "hypothesis — let visitors scan a sequence of stories in place while retaining the neighboring card for context"
evidence:
  - evidence_class: observed
    url: https://www.ikea.com/
    page_title: Hej! Welcome to IKEA Global
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Reject optional cookies, locate the Designer stories carousel, confirm Previous slide is disabled and Next slide is enabled, then activate Next slide.
    before: The carousel scrollLeft is 0; the visible cards are David Wahl (Puzzle perfect with ÖDLEBLAD) and Friso Wiersma (Behind the LÅDMAKARE system). Previous slide is disabled.
    after: The carousel scrollLeft is 336; the visible cards are Friso Wiersma (Behind the LÅDMAKARE system) and Wiebke Braasch (RISATORP is ready for anything). Previous slide and Next slide are enabled; the URL remains https://www.ikea.com/.
    screenshot: null
confidence: high
---

## Notes

The page lists nine story groups, while the carousel viewport displays two cards at once. Card identity and horizontal scroll position were compared before and after the click; the accessible snapshot also showed the Previous control changing from disabled to enabled.
