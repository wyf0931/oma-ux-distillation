---
record_type: observation
site: GitHub
page: Logged-out repository search results
context: Repository results for `react` are filtered to JavaScript; Sort by is Best match and the heading reports 4.5M results.
trigger: an active language facet and a sort control are visible on repository results
action: Select Most stars in the Sort by menu.
response:
  - The Sort by control changes to Most stars.
  - The URL adds `s=stars&o=desc` while retaining `q=react`, `language:JavaScript`, `l=JavaScript`, and `type=repositories`.
  - The heading remains at 4.5M results.
  - The first three results are react/react (251k stars), vercel/next.js (143k), and react/create-react-app (103k).
  - The visible result rows continue to display JavaScript as their language.
state: Repository ordering changes to Most stars while the query and JavaScript language facet remain active.
intent: see the most popular JavaScript repositories matching React
purpose: "hypothesis — let visitors change result order without losing the search and language scope"
evidence:
  - evidence_class: observed
    url: https://github.com/search?q=react+language%3AJavaScript&type=repositories&l=JavaScript
    page_title: Repository search results · GitHub
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Open logged-out GitHub repository search results for `react` filtered to JavaScript. Open Sort by and select Most stars. Inspect the URL, selected sort, result count, and first repositories.
    before: The URL contains `q=react`, `language:JavaScript`, `l=JavaScript`, and `type=repositories`; Sort by is Best match and the heading reports 4.5M results. The first result is react/react with 251k stars.
    after: The URL also contains `s=stars&o=desc` and retains the query, JavaScript filter, and repository type. Sort by is Most stars, the heading remains 4.5M results, and the first results are react/react (251k), vercel/next.js (143k), and react/create-react-app (103k); visible rows show JavaScript.
    screenshot: null
confidence: medium
---

## Notes

The result count and star totals are capture-time UI values. No repository was opened and no sign-in was used.
