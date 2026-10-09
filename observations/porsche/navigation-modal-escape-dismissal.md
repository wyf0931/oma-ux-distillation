---
record_type: observation
site: Porsche
page: France homepage primary navigation
context: The navigation modal is open after activating Menu; the underlying page is the Porsche France homepage.
trigger: keyboard dismissal while the navigation modal is open
action: Press Escape.
response:
  - The navigation modal closes.
  - The Porsche France homepage remains loaded at the same URL.
  - Focus is on the page body, not the Menu control.
state: The modal changes from open to closed without navigation; focus leaves the invoking control.
intent: dismiss navigation and return to homepage content
purpose: unknown
evidence:
  - evidence_class: observed
    url: https://www.porsche.com/france/
    page_title: Porsche France | Site officiel
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Activate Menu, press Escape, then take a fresh accessibility snapshot and inspect document.activeElement.
    before: The modal navigation is open; Menu had focus when the modal was activated.
    after: A fresh snapshot shows the modal absent; URL is unchanged; document.activeElement is BODY rather than Menu.
    screenshot: null
confidence: high
---

## Notes

The dismissal reproduced twice. The dialog was still present in the immediate snapshot after Escape but absent from a fresh snapshot; focus remained on BODY rather than returning to Menu.
