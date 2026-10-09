---
record_type: observation
site: GitHub
page: Unable to sign in recovery form
context: The public account-recovery form has an empty required email field, seven reason choices, and a disabled Submit button.
trigger: a visitor selects a reason on the account-recovery form
action: "Select ‘No account: I don't have a GitHub account’."
response:
  - The No account radio becomes checked.
  - The required email field and reason choices remain visible; no fields or destination change.
  - Submit remains disabled because the required email field is empty, and the URL does not change.
state: No reason selected with incomplete required field → No account selected with the same form and URL.
intent: unknown
purpose: "hypothesis — classify an account-access problem before support; any later routing is unknown"
evidence:
  - evidence_class: observed
    url: https://help.github.com/contact/cannot_sign_in
    page_title: Unable to sign in - GitHub 支持
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "From the logged-out Contact Us sign-in gate, choose Unable to sign in? Get help. On the resulting public recovery form, select ‘No account: I don't have a GitHub account’ without entering an email or submitting."
    before: The required email field is empty, no reason is selected, and Submit is disabled.
    after: No account is selected; the email field, other reason choices, disabled Submit button, page title, and URL remain unchanged.
    screenshot: null
confidence: low
---

## Notes

The reason selection alone did not change the current form. Submit was not enabled because email is required, and no email was entered. Whether the reason routes to different handling after submission is unobserved; this is a boundary, not a direct counterexample to request-type routing.
