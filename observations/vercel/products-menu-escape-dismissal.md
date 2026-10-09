---
record_type: observation
site: Vercel
page: Pricing page primary navigation
context: The Products menu is open over the Pricing page after activating Products.
trigger: keyboard dismissal while the navigation menu is open
action: Press Escape.
response:
  - The Products navigation menu closes.
  - The Products control returns to a collapsed state and receives focus.
  - The Pricing page remains loaded at the same URL.
state: The navigation changes from expanded to collapsed while preserving the current pricing page.
intent: dismiss navigation and return to the page content
purpose: "hypothesis — provide a keyboard dismissal path while preserving navigation context"
evidence:
  - evidence_class: observed
    url: https://vercel.com/pricing
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Activate Products in the Vercel Pricing page header, then press Escape and inspect the accessibility snapshot.
    before: Products is expanded and its destination menu is present over the Pricing page.
    after: Products is collapsed and focused; the menu is absent and the URL remains https://vercel.com/pricing.
    screenshot: null
confidence: high
---

## Notes

The accessibility snapshot marked Products as focused after the Escape keypress. Keyboard opening and touch behavior were not tested.
