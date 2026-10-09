---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: The Quick search dialog is open with an empty query. Blog is selected and CI/CD has keyboard focus after Tab.
trigger: a query-independent option has focus while a different option remains selected
action: Press ArrowDown once.
response:
  - Keyboard focus moves from CI/CD to Code review.
  - Blog remains selected; `aria-selected` stays true on Blog and false on the other options.
  - The query remains empty, the modal remains open, and the homepage URL is unchanged.
state: Blog is selected while CI/CD is focused → Blog remains selected while Code review is focused.
intent: unknown
purpose: "hypothesis — allow keyboard traversal of default shortcuts while preserving the active selection"
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "In an isolated logged-out context, open empty Quick search, press ArrowDown twice to select Blog, press Tab to focus CI/CD, then press ArrowDown once. Inspect document.activeElement and all options' aria-selected states."
    before: "Blog is aria-selected=true; CI/CD has focus; the query is empty and the modal is open."
    after: "Code review has focus; Blog remains aria-selected=true and the other options remain unselected. The query, modal, and URL remain unchanged."
    screenshot: null
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "Return to a fresh logged-out homepage. Open empty Quick search, select Blog with ArrowDown twice, Tab to CI/CD, then press ArrowDown once. Compare focus and selected states."
    before: "Blog is selected while CI/CD is focused in the empty-query suggestion list."
    after: "Code review has focus while Blog remains selected; the modal and homepage URL are unchanged."
    screenshot: null
confidence: low
boundaries: []
counterexamples: []
---

## Notes

The repeated state is confirmed by `document.activeElement` and each option's `aria-selected` attribute. This records the visible focus/selection behavior only; the intended keyboard model remains unknown.
