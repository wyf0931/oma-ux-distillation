---
record_type: observation
site: Vercel
page: Pricing
context: The Pricing page is open and Products in the primary navigation is collapsed.
trigger: keyboard focus reaches the Products navigation control
action: Press Enter while Products has focus.
response:
  - Products enters an expanded state.
  - Grouped product destinations become visible.
  - Focus moves to the first destination link, AI SDK.
  - The current Pricing page remains loaded at the same URL.
state: Primary navigation changes from collapsed to expanded by keyboard, and focus enters the revealed destination list.
intent: inspect and choose a product destination without using a pointer
purpose: "hypothesis — make the expanded navigation available through keyboard interaction while keeping focus in the revealed choices"
evidence:
  - evidence_class: observed
    url: https://vercel.com/pricing
    page_title: "Vercel Pricing: Hobby, Pro, and Enterprise plans"
    viewport: 1512x727
    browser: Chrome 154.0.0.0
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Load the Pricing page; press Tab three times until Products is focused; press Enter and inspect the accessibility snapshot.
    before: Products is collapsed; the Pricing page is loaded and no destination menu is visible.
    after: Products is expanded; grouped destination links are visible; AI SDK, the first destination link, has focus; the URL remains https://vercel.com/pricing.
    screenshot: null
confidence: high
---

## Notes

This records keyboard opening and focus movement only. Escape dismissal is recorded separately in [Products menu Escape dismissal](products-menu-escape-dismissal.md). Arrow-key traversal within the menu was not tested.
