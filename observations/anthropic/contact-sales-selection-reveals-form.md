---
record_type: observation
site: Anthropic
page: Contact sales request type
context: The Contact sales page shows a required “What can we help you with?” selector at its default value, with no contact fields visible.
trigger: explicit selection of a request type
action: Select Contact sales.
response:
  - Required fields appear for first name, last name, business email, phone number, company, website, job title, and industry.
  - The request-type selector remains visible with Contact sales selected.
  - The page URL remains unchanged.
state: The form changes from a request-type-only state to a Contact sales-specific field set.
intent: request information from Anthropic sales
purpose: "hypothesis — collect the fields needed for the selected inquiry type only after the visitor chooses that type"
evidence:
  - evidence_class: observed
    url: https://claude.com/contact-sales
    page_title: Contact sales | Claude by Anthropic
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public Contact sales page and select Contact sales in the request-type combobox. Do not fill any contact fields or submit.
    before: The request-type combobox shows Please select; contact fields are not present.
    after: Contact sales is selected and required contact fields appear; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

No personal data was entered and the form was not submitted.
