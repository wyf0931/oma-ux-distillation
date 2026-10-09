---
record_type: observation
site: Linear
page: Contact us
context: "Public contact hub titled ‘How can we help?’ with Sales, Support, and Other options."
trigger: "The visitor chooses a contact destination from the public contact hub."
action: "Click the Sales card, ‘Talk to sales.’"
response:
  - "The browser navigates to https://linear.app/contact/sales."
  - "The destination is titled ‘Contact sales’ and shows a dedicated form with Full name, Work email, Company size, and requirements fields."
  - "The page links to Contact support for technical issues or product questions."
state: "The contact hub is replaced by the Sales-specific contact page; the URL changes from /contact to /contact/sales."
intent: "Reach Linear's sales team about plans, pricing, enterprise contracts, or a demo."
purpose: "hypothesis — route visitors to a contact path that matches the kind of help they selected."
evidence:
  - evidence_class: observed
    url: https://linear.app/contact
    page_title: "Contact us – Linear"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open /contact in an isolated context, capture the Sales and Support choices, then click ‘Talk to sales.’"
    before: "The contact hub presents separate Sales and Support links beneath ‘How can we help?’"
    after: "The Sales link navigates to /contact/sales, which shows a sales-specific contact form and a link to Contact support. No form data was entered or submitted."
    screenshot: null
confidence: high
---

## Notes

The transition was observed through a public category link. The sales form was inspected only; no name, email, company size, or requirements were entered.
