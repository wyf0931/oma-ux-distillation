---
record_type: observation
site: GitHub
page: Zero-results recovery to Advanced search
context: Repository search for `codex-no-match-4829zxq` reports 0 results and offers an Advanced search link.
trigger: explicit selection of a zero-results recovery option
action: Activate the Advanced search link.
response:
  - The browser navigates to the Advanced search form.
  - The original query `codex-no-match-4829zxq` is prefilled in the Advanced search textbox.
  - Additional refinement fields are available for owners, repositories, language, dates, stars, forks, and other search criteria.
state: The zero-results page changes to Advanced search while preserving the original query for refinement.
intent: refine or repair a query that returned no repositories
purpose: "hypothesis — let visitors recover from zero results with advanced filters without retyping the query"
evidence:
  - evidence_class: observed
    url: https://github.com/search?q=codex-no-match-4829zxq&type=repositories
    page_title: Repository search results · GitHub
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: From the logged-out zero-results page for `codex-no-match-4829zxq`, activate the Advanced search link.
    before: The page reports 0 results and offers an Advanced search link with the query in its destination URL.
    after: The browser is at https://github.com/search/advanced?q=codex-no-match-4829zxq; the Advanced search textbox contains the original query.
    screenshot: null
confidence: high
---

## Notes

The form was inspected but not submitted. No result query or account action was made from the Advanced search page.
