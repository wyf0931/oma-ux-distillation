---
record_type: observation
site: Notion
page: Public signup email field
context: The Work email field contains `not-an-email`, is marked invalid, and exposes a Clear input control.
trigger: explicit activation of the invalid field's clear control
action: Activate Clear input.
response:
  - The email field is emptied.
  - The invalid state is cleared.
  - The signup page remains open and the Continue control is not activated.
state: The email field changes from invalid-value to empty/non-invalid state.
intent: remove the malformed value so it can be corrected
purpose: "hypothesis — give visitors a quick way to clear an invalid entry and recover"
evidence:
  - evidence_class: observed
    url: https://app.notion.com/signup
    page_title: Notion - 注册
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Enter the synthetic invalid value `not-an-email` in Work email, then activate the field's Clear input control.
    before: The field is marked invalid with `not-an-email`; Clear input is visible.
    after: The field is empty and no longer marked invalid; the page URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

No form submission occurred. A syntax-valid placeholder value was entered afterward, but no Continue action was taken.
