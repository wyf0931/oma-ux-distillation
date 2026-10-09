---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: "The Quick search modal is open with an empty Search or jump to combobox. Explore GitHub Actions, the first suggestion, is selected."
trigger: "A suggestion is active in the empty Quick search listbox."
action: "Press ArrowDown once."
response:
  - "The combobox retains focus and Explore Blog becomes the selected active option."
  - "The query remains empty, the modal stays open, and the homepage URL is unchanged."
state: "The active suggestion advances from GitHub Actions to Blog."
intent: "Move to the next default suggestion."
purpose: "hypothesis — provide sequential keyboard navigation through common destinations."
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: "GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open GitHub in a fresh isolated logged-out context, activate Search or jump to, press ArrowDown once to select GitHub Actions, then press ArrowDown again. Do not press Enter."
    before: "GitHub Actions is the selected option in the open empty Quick search list."
    after: "Blog is the selected option; the combobox retains focus and the modal and homepage URL remain unchanged."
    screenshot: null
confidence: high
---

## Notes

The selected option was confirmed in the accessibility snapshot and through the input's `aria-activedescendant` and option `aria-selected` values. No option was activated.
