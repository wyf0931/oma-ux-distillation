---
record_type: observation
site: Figma
page: Homepage primary navigation
context: The Products navigation region is open after activating Products.
trigger: keyboard dismissal while the navigation region is open
action: Press Escape.
response:
  - The Products navigation region closes.
  - The Products control returns to its collapsed state.
  - The homepage remains at the same URL.
state: The navigation changes from expanded to collapsed without a page transition.
intent: dismiss the product menu and return to homepage content
purpose: "hypothesis — provide a keyboard path to dismiss expanded navigation"
evidence:
  - evidence_class: observed
    url: https://www.figma.com/
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Activate Products in the primary navigation to open its menu, then press Escape and inspect the accessibility snapshot.
    before: Products is expanded and the Products navigation region with destination links is present.
    after: Products is collapsed and the menu region is absent; the homepage URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The menu closed after Escape. Focus return to the Products control was not verified.
