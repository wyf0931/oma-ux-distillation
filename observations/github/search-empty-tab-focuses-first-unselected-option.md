---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: The Quick search dialog is open with an empty combobox. GitHub Actions, Blog, CI/CD, and Code review are shown; no suggestion is active or selected.
trigger: the empty Quick search combobox has focus while query-independent suggestions are visible
action: Press Tab once.
response:
  - The GitHub Actions option receives keyboard focus.
  - Its `aria-selected` value remains false; no suggestion is selected.
  - The empty query, open dialog, and homepage URL remain unchanged.
state: The empty combobox is focused with no selection → GitHub Actions receives focus but remains unselected.
intent: move keyboard focus to the first search shortcut
purpose: "hypothesis — make the default search shortcuts reachable through keyboard navigation"
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "In an isolated logged-out context, open GitHub Quick search with no query and no selected suggestion. Press Tab once. Compare document.activeElement, each option's aria-selected state, the dialog, query, and URL."
    before: "The empty combobox has focus; GitHub Actions, Blog, CI/CD, and Code review are visible; all four options have aria-selected=false."
    after: "GitHub Actions has focus; all four options still have aria-selected=false. The query is empty, the dialog remains open, and the URL remains https://github.com/."
    screenshot: null
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "Return to a fresh homepage state, open empty Quick search, and press Tab once without entering a query. Inspect focused and selected states."
    before: "The empty combobox has focus; no suggestion is selected."
    after: "GitHub Actions has focus but remains unselected; the dialog, empty query, and homepage URL remain unchanged."
    screenshot: null
confidence: medium
boundaries: []
counterexamples: []
---

## Notes

The focus state was read from `document.activeElement`; the option stayed at `aria-selected=false`. This is distinct from ArrowDown, which selects the active suggestion. No destination was opened by Tab.
