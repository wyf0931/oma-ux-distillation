---
record_type: observation
site: GitHub
page: Logged-out repository search results
context: "Repository search results for ‘react’ are open with Sort by set to Best match and a result heading of about 7.3M repositories."
trigger: "A submitted search shows a result-ordering control."
action: "Select Most stars in the Sort by menu."
response:
  - "The Sort by control changes to Most stars."
  - "The URL adds `s=stars&o=desc` while retaining `q=react` and `type=repositories`."
  - "The first results are ordered by descending visible star counts: freeCodeCamp/freeCodeCamp (457k), react/react (251k), and vercel/next.js (143k)."
  - "The heading continues to report about 7.3M repository results."
state: "The search result ordering changes from Best match to Most stars while the query, repository result type, and displayed result count remain."
intent: "Find popular repositories matching React."
purpose: "hypothesis — let visitors prioritize a sortable result attribute without losing their query."
evidence:
  - evidence_class: observed
    url: https://github.com/search?q=react&type=repositories
    page_title: "Repository search results · GitHub"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open logged-out GitHub repository results for `react`, open Sort by, and select Most stars."
    before: "Sort by is Best match; the query is `react`, Repositories is the active result type, and the heading reports about 7.3M results. The first result is react/react with about 251k stars."
    after: "Sort by is Most stars; the URL contains `s=stars&o=desc` and retains `q=react&type=repositories`. The first results show freeCodeCamp/freeCodeCamp at 457k stars, react/react at 251k, and vercel/next.js at 143k. The result count remains about 7.3M. No repository was opened and no login was used."
    screenshot: null
confidence: high
---

## Notes

Star counts and result order are capture-time UI state. The page was left on the sorted result list; no repository was opened.
