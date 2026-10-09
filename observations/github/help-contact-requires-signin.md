---
record_type: observation
site: GitHub
page: GitHub Help portal Contact Us path
context: The public Help portal footer includes a “Contact Us” link under “Can’t find what you’re looking for?”.
trigger: a visitor chooses the Help portal's Contact Us entry
action: Click Contact Us.
response:
  - The browser navigates to `https://help.github.com/request/landing`.
  - The destination is titled “Sign in for Software Support and Product Help” and says a user can create a ticket or check an existing one.
  - The page offers GitHub sign-in, GHE sign-in, account creation, and a separate “Unable to sign in? Get help” path.
state: Public Help portal → sign-in gate for support tickets, with a separate account-recovery path.
intent: contact GitHub Support
purpose: "hypothesis — require account context for ticket creation while retaining a separate recovery path"
evidence:
  - evidence_class: observed
    url: https://help.github.com/
    page_title: "GitHub Help: GitHub Documentation, AI Search & Support"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: Open the public logged-out GitHub Help portal and activate Contact Us in the footer.
    before: The footer shows “Can’t find what you’re looking for?” and a Contact Us link.
    after: The browser loads `/request/landing`, titled “Sign in for Software Support and Product Help”. The page says users can create or check tickets and offers sign-in, account creation, and an Unable to sign in recovery path.
    screenshot: null
confidence: high
---

## Notes

No credentials were entered and no support ticket was created. This is a logged-out access path, not evidence about how authenticated requests are routed.
