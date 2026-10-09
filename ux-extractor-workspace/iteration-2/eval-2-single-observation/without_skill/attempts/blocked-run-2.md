---
record_type: observation
site: IKEA
page: "IKEA US sofas and sectionals listing; requested URL could not be opened"
context: "No page state was available because browser navigation did not start. The required public header text was therefore not verified."
trigger: "Attempt to open the requested public IKEA listing in a fresh research tab."
action: "No website control was operated; page creation failed before navigation."
response:
  - "Chrome DevTools MCP new_page and list_pages returned an error that the default Chrome profile was already running and requested an isolated browser instance."
  - "Retrying new_page with an isolated context returned the same browser-profile error."
  - "The connected browser inventory and tab creation returned nodeRepl.fetch request failed."
state: "Before: not observed. After: not observed. The page did not load, the public header was not verified, and Red (1) was not inspected or selected."
intent: unknown
purpose: unknown
evidence:
  - evidence_class: observed
    url: "https://www.ikea.com/us/en/cat/sofas-sectionals-fu003/?filters=f-price-buckets%3APRICE_0_50000"
    page_title: unknown
    viewport: unknown
    browser: "Chrome DevTools MCP and connected browser tab provider; navigation did not start"
    captured_at: "2026-10-09"
    tool: "Chrome DevTools MCP; CUA browser provider"
    reproduction: "Attempted to open the requested URL in a new Chrome DevTools MCP page, retried with isolatedContext, then attempted a new connected-browser tab. All attempts failed before page navigation."
    before: "No website state captured. Required public header text ‘Hej! Log in or sign up’ was not verified."
    after: "No website state captured. No filter was inspected or operated."
    screenshot: null
confidence: low
---

## Notes

This is a capture-limitation record, not evidence about IKEA's filter behavior. Chrome DevTools MCP reported that its default profile was already running and would not create or list pages; retrying with an isolated context returned the same error. The connected browser inventory and tab creation failed with `nodeRepl.fetch request failed`. The mandatory public header check could not be completed, so the `Red (1)` option was not inspected or clicked. Results count, filter state, and visible response remain unobserved. No account data was inspected, no website control was operated, and no formal corpus file was changed.
