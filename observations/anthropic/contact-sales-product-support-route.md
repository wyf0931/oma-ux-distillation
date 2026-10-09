---
record_type: observation
site: Anthropic
page: Contact sales request type
context: Contact sales is selected and its required contact fields are visible.
trigger: explicit change of the inquiry request type
action: Change the request type to Product support.
response:
  - The Contact sales field set disappears.
  - A message directs visitors to the Support Center with a direct link.
  - The Contact sales page remains loaded at the same URL.
state: The form changes from a Contact sales-specific field set to a Product support handoff.
intent: find support for an Anthropic product
purpose: "hypothesis — route each inquiry type to the appropriate information path and avoid collecting irrelevant contact details"
evidence:
  - evidence_class: observed
    url: https://claude.com/contact-sales
    page_title: Contact sales | Claude by Anthropic
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Select Contact sales to expose its fields, then select Product support. Do not fill fields or submit.
    before: Contact sales is selected and its contact fields are visible.
    after: Product support is selected; the form fields are replaced by a Support Center link; the URL is unchanged.
confidence: high
---

## Notes

The support destination was exposed without submitting contact details. Behavior for the other request types was not tested.
