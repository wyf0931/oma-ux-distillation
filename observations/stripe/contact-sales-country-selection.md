---
record_type: observation
site: Stripe
page: Contact Sales
context: "First step of the sales contact flow; the work email is blank and the country selector initially shows Singapore."
trigger: "The visitor opens the Country/Region selector."
action: "Select France from the country list."
response:
  - "The country selector displays France after the list closes."
  - "The Work email field and Continue button remain on the same step."
state: "Country/Region changes from Singapore to France; URL and visible form fields remain unchanged."
intent: "Choose the country relevant to the sales inquiry."
purpose: "hypothesis — collect regional context before directing the visitor to the correct contact page."
evidence:
  - evidence_class: observed
    url: https://stripe.com/zh-sg/contact/sales
    page_title: "Stripe | 联系我们的销售团队"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open Contact Sales in a clean isolated context, open Country/Region, select France, and inspect the form and URL."
    before: "Step 1 shows a blank Work email field, Country/Region set to Singapore, and Continue."
    after: "Country/Region shows France; the blank Work email field, Continue button, step heading, and URL are unchanged. No request-type selector is shown in this step."
    screenshot: null
confidence: high
---

## Notes

This records only the first-step response to country selection. No email was entered and Continue was not activated, so later steps and any regional routing remain unknown. This is boundary evidence for request-type-driven contact routing, not support for that candidate.
