---
record_type: observation
site: GitHub
page: Logged-out repository search zero-results state
context: The GitHub repository search has been submitted for `codex-no-match-4829zxq`.
trigger: submitted query returns zero matching repositories
action: Submit the query `codex-no-match-4829zxq` from Quick search.
response:
  - The results page reports 0 repository results.
  - The page states “Your search did not match any repositories”.
  - Recovery guidance offers expandable Search across an organization and Saved searches tips, plus an Advanced search link.
  - Other result types also show zero results.
state: A submitted search transitions to a repository zero-results state with alternative recovery paths.
intent: find repositories matching the entered query
purpose: "hypothesis — help visitors recover when a repository query has no matches"
evidence:
  - evidence_class: observed
    url: https://github.com/search?q=codex-no-match-4829zxq&type=repositories
    page_title: Repository search results · GitHub
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open GitHub while logged out, enter the unique query `codex-no-match-4829zxq`, and press Enter.
    before: Quick search contains the query and no query suggestions are available.
    after: Repository results report 0; the page shows an unmatched-query message and recovery tips.
    screenshot: null
confidence: high
---

## Notes

The query was chosen to produce a zero-result state; no repository, issue, or account content was accessed.
