---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: "The Quick search modal is open with an empty Search or jump to combobox and four Explore suggestions. No suggestion is active."
trigger: "The empty combobox and its suggestion list are open."
action: "Press ArrowDown once."
response:
  - "The combobox retains focus and GitHub Actions becomes the selected active option."
  - "The query remains empty, the modal stays open, and the homepage URL is unchanged."
state: "The empty Quick search moves from no active suggestion to Explore GitHub Actions."
intent: "Navigate the default suggestions with the keyboard."
purpose: "hypothesis — allow keyboard visitors to move through common destinations without entering a query."
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: "GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open GitHub in a fresh isolated logged-out context, activate Search or jump to, confirm the empty combobox and four Explore options, then press ArrowDown once. Do not press Enter."
    before: "The empty combobox is focused; GitHub Actions, Blog, CI/CD, and Code review are listed with no active option."
    after: "GitHub Actions is selected, the combobox remains focused, and the modal and homepage URL remain unchanged."
    screenshot: null
confidence: high
---

## Notes

The selected option was confirmed in the accessibility snapshot and through the input's `aria-activedescendant` and option `aria-selected` values. No option was activated.
