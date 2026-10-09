---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: "The Quick search modal is open with an empty combobox. Blog is the selected active suggestion; CI/CD is the next option in the list."
trigger: "A suggestion is selected in the open empty Quick search listbox."
action: "Press Tab once."
response:
  - "Keyboard focus moves from the combobox to the CI/CD option."
  - "Blog remains the selected active suggestion."
  - "The dialog remains open and the homepage URL is unchanged."
state: "Tab focuses CI/CD while the listbox selection remains on Blog."
intent: "Move keyboard focus to a suggestion or the next item in the search surface."
purpose: "hypothesis — provide keyboard access to suggestion destinations; the separation between focus and active selection needs further investigation."
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: "GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open GitHub in a fresh isolated logged-out context, activate Search or jump to, press ArrowDown twice to select Blog, then press Tab once. Do not press Enter or activate an option."
    before: "Blog is selected in the listbox while the Search or jump to combobox retains focus."
    after: "The CI/CD option has keyboard focus, Blog remains selected, the dialog stays open, and the homepage URL remains unchanged."
    screenshot: null
confidence: high
---

## Notes

The selected state was visible on Blog in the accessibility snapshot; the focus state was visible on CI/CD. `document.activeElement` was an anchor with `role=option`, while the URL and dialog state remained unchanged. No destination was activated.
