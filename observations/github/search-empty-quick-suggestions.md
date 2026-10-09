---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: The GitHub homepage shows a collapsed “Search or jump to” control.
trigger: explicit activation of the global search control
action: Activate Search or jump to.
response:
  - A modal Quick search dialog opens with an empty combobox.
  - "Four general Explore suggestions appear: GitHub Actions, Blog, CI/CD, and Code review."
  - A Search syntax tips link is also available.
  - The homepage remains at the same URL.
state: The homepage changes from a collapsed search control to an open empty-query Quick search dialog with default destination suggestions.
intent: begin a search or open a common GitHub destination
purpose: "hypothesis — offer common destinations before the visitor enters a query"
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the logged-out homepage, activate Search or jump to without entering a query.
    before: The search control is collapsed and no Quick search dialog is visible.
    after: The modal is open with an empty combobox, four Explore suggestions, and Search syntax tips; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The Explore suggestions are generic and not tied to a query. Entering “react” later cleared the suggestion list in this session; see [the separate no-suggestions observation](search-query-no-suggestions.md).
