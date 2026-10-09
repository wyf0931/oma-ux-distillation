---
record_type: observation
site: Vercel
page: Contact Sales form country field
context: The public Contact Sales form is loaded with Country set to Singapore; required lead fields are empty.
trigger: explicit selection of a different country
action: Change Country from Singapore to United States.
response:
  - The Country combobox changes to United States.
  - The same required contact fields remain visible.
  - The page remains on Contact Sales at the same URL.
state: The form's country value changes in place while the field set remains unchanged.
intent: identify the country associated with a sales inquiry
purpose: unknown
evidence:
  - evidence_class: observed
    url: https://vercel.com/contact/sales
    page_title: Contact Sales - Vercel
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the public Contact Sales form, open Country and select United States while the current value is Singapore.
    before: Country is Singapore; the contact form fields are empty.
    after: Country is United States; the same fields remain visible and the URL is unchanged.
    screenshot: null
confidence: medium
---

## Notes

No contact details were entered and the form was not submitted. No conditional field changes were observed for this country selection.
