---
record_type: observation
site: Notion
page: Pricing page language selector
context: The English Pricing page is loaded; the footer language control shows English (US).
trigger: explicit selection of a language/region option
action: Open the language control and select Français (France).
response:
  - The browser navigates from `/pricing` to `/fr/pricing`.
  - The page title, navigation labels, and pricing content change to French.
  - The current page remains the Pricing page.
state: The English Pricing page changes to its French counterpart while retaining the pricing path.
intent: read pricing information in French
purpose: "hypothesis — let visitors change locale while keeping the current content destination"
evidence:
  - evidence_class: observed
    url: https://www.notion.com/pricing
    page_title: "Notion Pricing Plans: Free, Plus, Business, & Enterprise."
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the Pricing page, activate English (US), then select Français (France) in the Languages dialog.
    before: The URL is https://www.notion.com/pricing; the page is in English and the language dialog lists Français (France).
    after: The URL is https://www.notion.com/fr/pricing; page title, navigation, and content are in French; the Pricing page remains open.
    screenshot: null
confidence: high
---

## Notes

The chooser offers language/region pairs. Persistence across visits and other Notion page types were not tested.
