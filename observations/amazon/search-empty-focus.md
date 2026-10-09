---
record_type: observation
site: Amazon
page: US homepage search
context: The Amazon homepage header shows an empty Search Amazon field and the homepage shopping content below.
trigger: explicit activation of the empty search field
action: Focus Search Amazon without entering a query.
response:
  - The search field receives focus.
  - No search-specific shortcut list or suggestion panel appears.
  - The homepage shopping content remains visible.
  - The page URL is unchanged.
state: The empty search field changes from unfocused to focused; no search-suggestion state appears.
intent: begin searching for a product
purpose: unknown
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/
    page_title: Amazon.com. Spend less. Smile more.
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public US homepage and focus Search Amazon without typing or submitting.
    before: The search field is empty and unfocused; homepage shopping content is visible.
    after: The empty field is focused; no search-specific shortcut panel appears and the homepage remains at the same URL.
    screenshot: null
confidence: high
---

## Notes

This is one logged-out/homepage search state. It does not establish whether suggestions appear after query entry or on other Amazon pages.
