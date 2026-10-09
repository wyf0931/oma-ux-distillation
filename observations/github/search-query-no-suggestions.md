---
record_type: observation
site: GitHub
page: Logged-out homepage Quick search
context: The Quick search dialog is open with an empty “Search or jump to” field and four general Explore suggestions.
trigger: text entry in the global quick-search field
action: Enter “react” without submitting.
response:
  - The combobox retains the query “react”.
      - The Search suggestions listbox contains no options after the query is entered.
  - The Search syntax tips link remains available.
  - The page URL stays at the homepage.
state: The empty-query Explore suggestions disappear; no query-specific suggestions replace them.
intent: search GitHub for React-related destinations
purpose: unknown
evidence:
  - evidence_class: observed
    url: https://github.com/
    page_title: GitHub · Change is constant. GitHub keeps you ahead. · GitHub
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the logged-out homepage, open Search or jump to, note the empty-query Explore suggestions, then enter “react” without pressing Enter.
    before: The empty search dialog lists Explore GitHub Actions, Explore Blog, Explore CI/CD, and Explore Code review.
    after: The field contains “react”; the suggestions listbox is empty; Search syntax tips remains; the URL is unchanged.
    screenshot: null
  - evidence_class: observed
    url: https://github.com/
    page_title: "GitHub · Change is constant. GitHub keeps you ahead. · GitHub"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "In a fresh logged-out context, open Quick search and type ‘react’ with keyboard input; inspect the listbox immediately and again after about 3.5 seconds."
    before: "The empty Quick search shows Explore destinations and a Search syntax tips link."
    after: "The combobox retains ‘react’. The suggestions listbox remains empty after about 3.5 seconds, aria-busy is false, and Search syntax tips remains. The URL stays at the GitHub homepage."
    screenshot: null
confidence: high
---

## Notes

This records a logged-out homepage Quick search state reproduced in two captures; the second used actual keyboard input and waited about 3.5 seconds. It does not establish whether authenticated search, other query lengths, or other GitHub search surfaces return suggestions.
