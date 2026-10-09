---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: The Quick search dialog contains the query `react`. The suggestions listbox is empty and Search syntax tips remains available.
trigger: a nonempty query is present in the Quick search field and the Clear search control is visible
action: Activate Clear search.
response:
  - The combobox value becomes empty.
  - The Explore list returns with GitHub Actions, Blog, CI/CD, and Code review in that order; none is selected.
  - Search syntax tips remains available and the homepage URL does not change.
state: "`react` query with no suggestions → empty query with the default Explore shortcuts restored."
intent: clear the current query and return to the default search choices
purpose: "hypothesis — let visitors restart discovery from the empty-search shortcuts"
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "In an isolated logged-out context, open Quick search, type `react` without submitting, confirm the suggestions list is empty, then activate Clear search. Compare the query, shortcut list and order, Search syntax tips, selected state, and URL."
    before: "The field contains `react`; the suggestions listbox has no options; Search syntax tips is present; the URL is the homepage."
    after: "The field is empty; Explore lists GitHub Actions, Blog, CI/CD, and Code review in that order with none selected; Search syntax tips remains; the URL is unchanged."
    screenshot: null
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "Repeat in a fresh homepage state: enter `react` in Quick search without submitting, then activate Clear search. Inspect the restored empty-query state."
    before: "The field contains `react` and the suggestions listbox is empty."
    after: "The field is empty; the four default Explore shortcuts return in the same order, none selected; Search syntax tips and the homepage URL remain."
    screenshot: null
confidence: high
boundaries: []
counterexamples: []
---

## Notes

The empty-query shortcut list returned after clearing the query in two isolated Playwright captures. This records clear-and-reset behavior; it does not show that GitHub provides query-specific suggestions for `react`.
