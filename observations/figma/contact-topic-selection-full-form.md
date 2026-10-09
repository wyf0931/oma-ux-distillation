---
record_type: observation
site: Figma
page: Contact Us — full sales form
context: The full Contact sales form is visible on `/contact/`; the required topic combobox is empty, and Work email, First name, Last name, and Company name are required.
trigger: a required topic combobox is available in the sales form
action: Select Billing and invoicing in Which topic best fits your needs?
response:
  - The topic combobox displays Billing and invoicing.
  - The same Work email, First name, Last name, Company name, and Phone number fields remain visible.
  - The page URL remains https://www.figma.com/contact/.
state: The topic value changes from empty to Billing and invoicing; the visible sales form fields remain unchanged.
intent: categorize the sales inquiry
purpose: "hypothesis — classify the inquiry for later handling; any next-step routing or field changes were not tested"
evidence:
  - evidence_class: observed
    url: https://www.figma.com/contact/
    page_title: "Contact Us | Figma"
    viewport: unknown
    browser: unknown
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: In the full Contact sales form, open Which topic best fits your needs? and select Billing and invoicing. Do not enter contact details or submit.
    before: The topic combobox is empty; Work email, First name, Last name, and Company name are required; Phone number is optional.
    after: The topic combobox displays Billing and invoicing; the same contact fields remain visible and the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The form was in a full single-page layout with a separate support link. No contact details were entered, the plan selector was not changed, and Submit was not activated. Later routing remains unknown.
