---
record_type: observation
site: Mistral AI
page: Homepage language switcher
context: The English homepage is loaded; the Language switcher is collapsed and offers English and Français.
trigger: explicit selection of a language option
action: Select Français.
response:
  - The browser navigates from the root homepage URL to the French locale URL `/fr/`.
  - Homepage headings, navigation labels, and body content are shown in French.
  - The visitor remains on the homepage rather than a different content destination.
state: The current homepage changes from English at `/` to French at `/fr/`.
intent: view the site in French
purpose: "hypothesis — change the site language while retaining the current page context"
evidence:
  - evidence_class: observed
    url: https://mistral.ai/
    page_title: Mistral | #1 in Sovereign AI: Frontier Open Models You Own
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the English homepage, dismiss the cookie widget without accepting, open Language switcher, and select Français.
    before: The page URL is https://mistral.ai/; navigation and homepage content are in English.
    after: The page URL is https://mistral.ai/fr/; navigation and homepage content are in French.
    screenshot: null
confidence: high
---

## Notes

The selected locale was directly visible in both the resulting URL and translated page content. Persistence across later visits and locale changes from non-home pages were not tested.
