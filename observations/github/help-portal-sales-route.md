---
record_type: observation
site: GitHub
page: GitHub Help portal
context: "The public GitHub Help portal has a Support navigation link and a separate GitHub Sales destination described as help finding the best plan for a team or organization."
trigger: "A visitor looking for help encounters a sales-specific contact path in the Help portal."
action: "Click GitHub Sales."
response:
  - "The browser navigates to github.com/enterprise/contact."
  - "The destination is headed ‘Talk to our sales team’ and describes a demo, trial, and plan guidance."
  - "The page offers an Enterprise Support link for existing installation questions."
  - "A sales form is shown, with required fields; no field is completed or submitted."
state: "The Help portal is replaced by a sales-specific page and form; the URL changes to /enterprise/contact with a source query string."
intent: "Talk to GitHub Sales about plans or enterprise use."
purpose: "hypothesis — direct visitors with a sales need to the sales team while offering a separate path for existing-customer support."
evidence:
  - evidence_class: observed
    url: https://help.github.com/
    page_title: "GitHub Help: GitHub Documentation, AI Search & Support"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the public GitHub Help portal in an isolated context and click the GitHub Sales link."
    before: "The Help portal presents a GitHub Sales link described as helping teams choose a plan; a separate Support navigation item is also visible."
    after: "The GitHub Sales link opens /enterprise/contact, a sales-specific page with demo/plan copy, required sales fields, and an Enterprise Support link. All fields remain blank and the form is not submitted."
    screenshot: null
confidence: high
---

## Notes

This records the public handoff to GitHub Sales and the logged-out destination. No name, company, email, phone number, or message was entered.
