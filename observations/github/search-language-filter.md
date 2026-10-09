---
record_type: observation
site: GitHub
page: Logged-out repository search results
context: Repository results for `react` are open, with a Languages filter listing JavaScript and other options.
trigger: explicit selection of a result refinement
action: Select JavaScript in the Languages filter.
response:
  - The search URL adds `language:JavaScript` and `l=JavaScript`.
  - The heading updates to “Search Results · react language:JavaScript”.
  - The repository result count changes from about 7.3M to 4.5M.
  - The page remains on repository results.
state: The broad `react` repository result set changes to a JavaScript-filtered result set.
intent: narrow React repository results to JavaScript projects
purpose: "hypothesis — refine a broad result set using a domain-specific facet"
evidence:
  - evidence_class: observed
    url: https://github.com/search?q=react&type=repositories
    page_title: Repository search results · GitHub
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the logged-out repository results for `react`, select JavaScript in the Languages filter.
    before: Repository search is for `react`; about 7.3M repositories are reported and JavaScript is available under Languages.
    after: The URL is https://github.com/search?q=react+language%3AJavaScript&type=repositories&l=JavaScript; the heading includes `language:JavaScript` and about 4.5M repositories are reported.
    screenshot: null
confidence: high
---

## Notes

Counts are the values shown at capture time and may change. The filtered result set was not paginated or sorted.
