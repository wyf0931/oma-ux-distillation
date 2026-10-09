---
record_type: observation
site: DuckDuckGo / Duck.ai
page: Search results
context: "The DuckDuckGo homepage search field contains ‘running shoes’ and its query action list offers Search and Ask Duck.ai."
trigger: "The visitor chooses a route for the entered query."
action: "Select Search from the query action list."
response:
  - "The browser navigates to a web-results page with the query preserved in the URL and search field."
  - "The page displays results from multiple sources and tabs for All, Images, Videos, News, and Maps."
  - "Search Assist, Duck.ai, location, safe-search, and time controls are available on the results page."
state: "The homepage query action list is replaced by a web-results page; ‘running shoes’ remains the active query."
intent: "View web results for the entered query."
purpose: "hypothesis — transition from query entry to a result set while retaining the query for further exploration."
evidence:
  - evidence_class: observed
    url: https://duckduckgo.com/
    page_title: "running shoes at DuckDuckGo"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the homepage in an isolated context, type ‘running shoes’, then choose Search from the query action list."
    before: "The homepage search field contains the query and the listbox offers Search and Ask Duck.ai."
    after: "The browser opens https://duckduckgo.com/?ia=web&origin=funnel_home_website&t=h_&q=running+shoes. The results page keeps the query, displays web results, and offers result-type tabs and search filters."
    screenshot: null
confidence: high
---

## Notes

The synthetic query was used only to inspect the public search flow. No result was opened, and the query was not sent to Duck.ai.
