---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: Quick search is open on the logged-out homepage with an empty combobox, four default Explore shortcuts, and Search syntax tips.
trigger: text entry in the global Quick search field
action: Enter `issues` without submitting.
response:
  - The combobox retains `issues`.
  - "The suggestion list narrows to one query-related option: Explore Issues."
  - Search syntax tips remains available and the homepage URL does not change.
state: Empty query with four default Explore shortcuts → query `issues` with a single Explore Issues suggestion.
intent: find GitHub Issues
purpose: "hypothesis — offer a destination suggestion related to the entered search term"
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "In an isolated logged-out context, open GitHub Quick search and enter `issues` without submitting. Inspect the query, listbox options, syntax link, and URL."
    before: "The combobox is empty; the Explore list shows GitHub Actions, Blog, CI/CD, and Code review. Search syntax tips is visible."
    after: "The combobox contains `issues`; the only suggestion is Explore Issues; Search syntax tips remains and the URL is unchanged."
    screenshot: null
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: 1280x720 CSS pixels
    browser: Chrome 154 (Playwright CLI 0.1.22, headless)
    captured_at: "2026-10-09"
    tool: Playwright CLI
    reproduction: "Clear the prior query, confirm the empty Quick search state, then enter `issues` again without submitting. Inspect the restored query-dependent option."
    before: "The combobox is empty and the default Explore shortcuts are visible."
    after: "The combobox contains `issues`; Explore Issues is the only suggestion and the URL remains on the homepage."
    screenshot: null
confidence: high
boundaries: []
counterexamples: []
---

## Notes

GitHub showed query-guided assistance for `issues`, while [typing `react`](search-query-no-suggestions.md) left the listbox empty. This is a query-specific distinction, not evidence of consistent suggestions for every query or GitHub search surface.
