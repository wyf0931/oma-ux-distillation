---
record_type: observation
site: GitHub
page: Logged-out repository search results
context: The Quick search dialog contains “react”; the logged-out homepage showed no query-specific suggestions for that value.
trigger: explicit submission of the search query
action: Press Enter while “react” is in the Search or jump to combobox.
response:
  - The browser navigates to the repository search results page for `react`.
  - Repositories is the active result type and the page reports about 7.3M results.
  - Result-type links are available for Code, Issues, Pull requests, Discussions, and Users.
  - Language filters such as JavaScript, TypeScript, HTML, and CSS are available.
state: The quick-search dialog changes to a repository results page with result-type and language refinement options.
intent: find repositories related to React
purpose: "hypothesis — make a broad search refinable by content type and programming language"
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the logged-out homepage; enter “react” in Search or jump to, then press Enter.
    before: The modal search contains “react”; its suggestions listbox is empty and Search syntax tips remains.
    after: The browser is at https://github.com/search?q=react&type=repositories with Repositories selected, about 7.3M results, result-type tabs, and language-filter links.
    screenshot: null
confidence: high
---

## Notes

No result was opened and no account action was taken. The result count is the count displayed at capture time and may change.
