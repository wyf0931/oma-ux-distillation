---
record_type: observation
site: IKEA
page: US sofa category and filters
context: "Requested URL; page state unavailable because the browser did not open the page."
trigger: research browser unavailable
action: "not performed: the page was not opened, so no filter control was inspected or selected"
response:
  - "Chrome DevTools MCP returned an error for both isolated and fresh-tab attempts: the browser is already running and requested an isolated instance could not be started."
state: "Before state: unavailable; after state: unavailable; no IKEA page interaction was performed."
intent: unknown
purpose: unknown
evidence:
  - evidence_class: observed
    url: "https://www.ikea.com/us/en/cat/sofas-sectionals-fu003/?filters=f-price-buckets%3APRICE_0_50000"
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Attempted to open the exact public URL in an isolated context, then attempted a fresh tab without isolatedContext. Both new_page calls failed before returning a page."
    before: "No page snapshot or public header was available."
    after: "No page snapshot or public header was available."
    screenshot: null
confidence: low
---

## Notes

This is a capture-failure record, not evidence of IKEA's filter behavior. The isolated-context attempt failed because the DevTools Chrome profile was already running. The fresh-tab fallback returned the same browser-running error. The required public header text could not be verified, so no page content was inspected and no control was clicked. Results count, filter state, and response remain unobserved.
