---
record_type: observation
site: Notion
page: Public signup email field
context: The Notion signup form is open with an empty Work email field and a Continue button.
trigger: text entry in an email field
action: Enter the synthetic value `not-an-email`, then move focus to Continue without activating it.
response:
  - The field retains the entered value and is marked invalid in the accessibility snapshot.
  - No visible or associated textual validation message appears after blur.
  - The signup page remains open at the same URL.
state: The empty Work email field changes to an invalid-value state without a visible correction message.
intent: provide an email to start an account
purpose: unknown
counterexamples:
  - "Direct counterexample to Inline Email Format Validation Feedback: the field is invalid after blur but no text guidance appears."
evidence:
  - evidence_class: observed
    url: https://app.notion.com/signup
    page_title: Notion - 注册
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the public signup page, enter `not-an-email` in Work email and press Tab; do not activate Continue.
    before: Work email is empty; Continue is visible.
    after: The textbox value is `not-an-email` and the snapshot marks it invalid; no error description is present; URL is unchanged.
    screenshot: null
confidence: medium
---

## Notes

The input was synthetic and the form was not submitted. The screenshot showed no visible error message; whether Continue triggers further validation was not tested.
