---
record_type: observation
site: Nike
page: Mexico Help contact form
context: The public Support Team form is open at `/mx/help/ask`; Category is unselected, the contact fields are empty, and Continue is disabled.
trigger: a Category selector is available in the support request form
action: Select Track My Order in Category.
response:
  - The Category selector changes to Track My Order.
  - The same Subject, First Name, Last Name, Email Address, Re-enter Email Address, Order Number, and Question fields remain visible.
  - Order Number is not marked required in the accessibility snapshot, and Continue remains disabled.
  - The page URL remains unchanged.
state: The selected request category changes while the visible fields and disabled Continue state remain unchanged.
intent: find help for an order-tracking issue
purpose: "hypothesis — classify the support request before any later handling; subsequent routing is untested"
evidence:
  - evidence_class: observed
    url: https://www.nike.com/mx/help/ask
    page_title: Nike
    viewport: 1280x727
    browser: Chrome 154.0.0.0
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public Mexico Help form, select Track My Order in Category, and inspect the fields and Continue state. Do not enter contact or order information and do not activate Continue.
    before: Category is unselected; the listed request fields are empty; Order Number is not marked required; Continue is disabled.
    after: Category displays Track My Order; the same fields remain; Order Number is not marked required; Continue is disabled and the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

No personal or order information was entered. The behavior of Continue and any later routing remain unobserved.
