---
record_type: observation
site: Linear
page: Contact us
context: "Public contact hub titled ‘How can we help?’ with Sales, Support, and Other options."
trigger: "The visitor chooses a contact destination from the public contact hub."
action: "Click the Support card, ‘Contact support.’"
response:
  - "The browser navigates to https://linear.app/contact/support."
  - "The destination lists product questions, problem reports, and feedback as support topics."
  - "The page offers a Log in link and a support email address; no support form is shown in the logged-out state."
  - "The page links to Contact sales for questions about plans, pricing, or demos."
state: "The contact hub is replaced by the Support-specific page; the URL changes from /contact to /contact/support."
intent: "Reach Linear's support team about a question, problem, or feedback."
purpose: "hypothesis — route visitors to a contact path that matches the kind of help they selected."
evidence:
  - evidence_class: observed
    url: https://linear.app/contact
    page_title: "Contact us – Linear"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open /contact in an isolated context, capture the Sales and Support choices, then click ‘Contact support.’"
    before: "The contact hub presents separate Sales and Support links beneath ‘How can we help?’"
    after: "The Support link navigates to /contact/support. The logged-out page describes support topics, offers login or a support email, and links back to Contact sales. No message was sent and no account was accessed."
    screenshot: null
confidence: high
---

## Notes

This records public navigation and logged-out page content only. No support request was sent and no login was attempted.
