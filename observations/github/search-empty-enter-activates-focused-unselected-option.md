---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: The Quick search dialog is open with an empty query. GitHub Actions has keyboard focus after Tab, but no suggestion is selected (`aria-selected=false`).
trigger: a query-independent suggestion has keyboard focus in the empty Quick search list
action: Press Enter.
response:
  - The browser navigates to `https://github.com/features/actions`.
  - The page title changes to “GitHub Actions · CI/CD and automations · Agentic Workflows · Workflows · GitHub”.
state: Empty Quick search with GitHub Actions focused and unselected → GitHub Actions landing page.
intent: open the focused GitHub Actions destination
purpose: "hypothesis — let Enter activate a keyboard-focused shortcut even before it is marked selected"
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "In an isolated logged-out context, open GitHub Quick search with no query and no selected suggestion. Press Tab to focus GitHub Actions, verify aria-selected=false, then press Enter. Inspect the destination URL and title."
    before: "GitHub Actions has keyboard focus but aria-selected=false; the query is empty and the Quick search dialog is open."
    after: "The browser loads https://github.com/features/actions with the GitHub Actions page title."
    screenshot: null
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "Return to the logged-out GitHub homepage, reopen empty Quick search, press Tab to focus GitHub Actions without selecting it, and press Enter. Inspect the destination."
    before: "GitHub Actions has focus, aria-selected=false, and no query is entered."
    after: "The browser loads https://github.com/features/actions with the GitHub Actions page title."
    screenshot: null
confidence: high
boundaries: []
counterexamples: []
---

## Notes

In two reproductions, Enter activated the focused unselected GitHub Actions option. This contrasts with [the separate selected/focused mismatch observation](search-empty-enter-opens-selected-option.md), where Blog remained selected while CI/CD had focus and Enter opened Blog. The activation rule when focus and selection differ remains unclear.
