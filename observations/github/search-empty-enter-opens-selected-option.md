---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: Quick search is open with an empty query. “Explore Blog” remains selected while keyboard focus is on “Explore CI/CD”.
trigger: an option remains selected in the expanded empty-search list
action: Press Enter while “Explore CI/CD” has focus and “Explore Blog” remains selected.
response:
  - The browser navigates to https://github.blog/.
  - The destination page title is “Home - The GitHub Blog”.
state: Empty Quick search with Blog selected and CI/CD focused → GitHub Blog home page.
intent: unknown
purpose: "hypothesis — allow keyboard activation of a selected search shortcut; the focus and selection mismatch makes intended target ambiguous"
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: Home - The GitHub Blog
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Open the logged-out GitHub homepage Quick search with an empty query. Press ArrowDown twice to select Explore GitHub Actions and then Explore Blog. Press Tab once so Explore CI/CD receives focus while Explore Blog remains selected, then press Enter. Inspect the resulting URL and page title.
    before: Quick search is open with a blank query. Explore Blog is marked selected; Explore CI/CD is focusable and focused.
    after: The browser loads https://github.blog/ with the title “Home - The GitHub Blog”.
    screenshot: null
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub · GitHub
    viewport: unknown
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: In a second fresh isolated context, open empty Quick search, press ArrowDown twice, then Tab once and Enter. Observe the selected/focused options before Enter and inspect the destination.
    before: Explore Blog is selected while Explore CI/CD is focused in the empty-query suggestion list.
    after: Enter again opens https://github.blog/; the selected/focused mismatch was reproduced.
    screenshot: null
confidence: low
---

## Notes

The accessibility snapshot exposed a mismatch between the selected option (Blog) and the focused option (CI/CD). Enter navigated to Blog in two fresh isolated contexts. This confirms the response for this sequence, but not whether the selected/focused mismatch is intended or a focus-management defect. The destination is public GitHub Blog content; no signed-in workspace or account content was accessed.
