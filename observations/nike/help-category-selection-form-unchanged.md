---
record_type: observation
site: Nike
page: Mexico Help contact form
context: The public Support Team form is open at `/mx/help/ask`; Category is unselected and all contact and question fields are empty.
trigger: a Category selector is available in the support request form
action: Select Product Info / Support.
response:
  - The Category selector changes from empty to Product Info / Support.
  - The visible Subject, First Name, Last Name, Email Address, Re-enter Email Address, Order Number, and Question fields remain unchanged.
  - The page URL remains unchanged; Continue is not activated.
state: The request category becomes selected while the same support-form fields remain visible.
intent: classify the support inquiry
purpose: "hypothesis — collect a request category before the support inquiry is submitted; whether it changes later routing is untested"
evidence:
  - evidence_class: observed
    url: https://www.nike.com/mx/help/ask
    page_title: Nike
    viewport: 1512x727
    browser: Chrome for Testing 151.0.7922.34
    captured_at: "2026-10-08"
    tool: Playwright CLI 0.1.22
    reproduction: Open the public Nike Help form in a temporary context, choose Product Info / Support in Category, and inspect the visible fields. Do not enter contact details or activate Continue.
    before: Category is empty; Subject, First Name, Last Name, Email Address, Re-enter Email Address, Order Number, and Question fields are visible and empty.
    after: Category displays Product Info / Support; the same fields remain visible and empty; URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

No personal information was entered and Continue was not activated. Any later routing or category-specific fields remain unobserved.
