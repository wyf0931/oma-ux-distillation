---
record_type: observation
site: Netflix
page: Tudum homepage language selector
context: The English Tudum homepage is open at `/tudum`; the language selector shows English.
trigger: the language selector offers a second language option
action: Select Português from the language selector.
response:
  - The browser navigates to `/tudum/pt-br`.
  - The selector shows Português and the page title changes to “Netflix Tudum - Muito além do streaming”.
  - The Tudum homepage remains open with translated navigation and sections including Destaque, Favoritos dos fãs, and Últimas notícias.
state: The Tudum homepage changes from English to Brazilian Portuguese while preserving the homepage content destination.
intent: read the Tudum homepage in Portuguese
purpose: "hypothesis — let visitors change language without losing the current content destination"
evidence:
  - evidence_class: observed
    url: https://www.netflix.com/tudum
    page_title: Netflix Tudum - Go behind the streams
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public English Tudum homepage, open the language selector, and choose Português.
    before: The URL is https://www.netflix.com/tudum; the selector shows English and the page title is Netflix Tudum - Go behind the streams.
    after: The URL is https://www.netflix.com/tudum/pt-br; the selector shows Português, the title and visible navigation/content are in Portuguese, and Tudum homepage sections remain present.
    screenshot: null
confidence: high
---

## Notes

The language option was selected from the public Tudum homepage. The site changed to a locale-prefixed Tudum route rather than an unrelated regional landing page. Persistence across visits was not tested.
