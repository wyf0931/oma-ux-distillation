---
record_type: observation
site: Mistral AI
page: Research page language switcher
context: The French Research page is loaded at `/fr/research/`; the Language switcher is collapsed.
trigger: explicit selection of a language option on a non-homepage page
action: Open Language switcher and select English.
response:
  - The browser navigates to `/research/`.
  - The page title changes to “AI Research | Mistral”.
  - Navigation labels and page content change to English.
  - The current page remains the Research page.
state: The French Research page changes to the English Research page while preserving the page type and path.
intent: read the Research page in English
purpose: "hypothesis — switch language while retaining the current content destination"
evidence:
  - evidence_class: observed
    url: https://mistral.ai/fr/research/
    page_title: Recherche en IA | Mistral
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the French Research page, open its Language switcher, and select English.
    before: The current URL is https://mistral.ai/fr/research/; page title and navigation are in French.
    after: The current URL is https://mistral.ai/research/; title and navigation are in English; the Research page remains open.
    screenshot: null
confidence: high
---

## Notes

This confirms same-page-type locale switching on Mistral's Research page. Other content types and persistence were not tested.
