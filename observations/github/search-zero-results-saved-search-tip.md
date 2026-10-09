---
record_type: observation
site: GitHub
page: Logged-out repository search zero-results recovery
context: A repository search shows 0 results; the “Saved searches” recovery disclosure is collapsed.
trigger: explicit activation of a zero-results recovery tip
action: Expand “Saved searches”.
response:
  - The Saved searches disclosure enters an expanded state.
  - "Guidance appears: visitors who repeatedly search the same organization or repository set can save a query from the search page."
  - The zero-results page remains open at the same URL.
state: The collapsed recovery tip changes to an expanded explanation while preserving the zero-results context.
intent: understand how to reuse a recurring search
purpose: "hypothesis — help visitors keep a useful query for repeated searches"
evidence:
  - evidence_class: observed
    url: https://github.com/search?q=codex-no-match-4829zxq&type=repositories
    page_title: Repository search results · GitHub
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the logged-out zero-results page, expand the collapsed Saved searches tip.
    before: The page reports 0 repository results and Saved searches is collapsed.
    after: The disclosure is expanded with guidance about saving recurring searches; URL and zero-results state are unchanged.
    screenshot: null
confidence: medium
---

## Notes

The displayed guidance was observed. Whether a logged-out visitor can save a search, or what happens after choosing the save control, was not tested.
