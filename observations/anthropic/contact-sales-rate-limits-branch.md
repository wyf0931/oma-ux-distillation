---
record_type: observation
site: Anthropic
page: Contact sales request type
context: Product support is selected and the form area points to the Support Center.
trigger: explicit change of the inquiry request type
action: Change the request type to Increase rate limits.
response:
  - Required contact fields appear for first name, last name, business email, company name, and company website.
  - An Organization ID field appears with instructions to find it in account settings.
  - The Contact sales page remains loaded at the same URL.
state: The Product support handoff changes to a rate-limits form with an Organization ID requirement.
intent: request higher API rate limits
purpose: "hypothesis — collect account and organization context needed to evaluate a rate-limit request"
evidence:
  - evidence_class: observed
    url: https://claude.com/contact-sales
    page_title: Contact sales | Claude by Anthropic
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Select Product support in the request-type selector, then select Increase rate limits. Do not fill fields or submit.
    before: Product support is selected and the form area displays a Support Center link.
    after: Increase rate limits is selected and the tailored contact form with Organization ID instructions is visible; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

No account identifiers or contact details were entered. Submitting the request was not tested.
