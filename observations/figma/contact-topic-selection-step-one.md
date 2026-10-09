---
record_type: observation
site: Figma
page: Contact Us
context: Step 1 of the public Contact Us form is open; the required topic selector is empty and the required First Name, Last Name, and Work Email Address fields are visible.
trigger: a required topic selector is available before advancing the contact flow
action: Select Technical and product support from Which topic best suits your needs?
response:
  - The topic selector displays Technical and product support.
  - The First Name, Last Name, and Work Email Address fields remain visible and required.
  - The Next step button remains visible.
  - The current URL remains unchanged.
state: The selected topic changes from empty to Technical and product support; the visible Step 1 fields remain the same.
intent: identify the reason for contacting Figma
purpose: "hypothesis — classify a contact request before advancing to a later step; any later routing or field changes were not observed"
evidence:
  - evidence_class: observed
    url: https://www.figma.com/contact/
    page_title: "Contact Us | Figma"
    viewport: 1512x727
    browser: Chrome 154.0.0.0
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open Contact Us, open Which topic best suits your needs?, and choose Technical and product support. Do not enter contact details or activate Next step.
    before: The form shows Step 1 of 2; First Name, Last Name, and Work Email Address are required; the topic combobox has no selected value.
    after: The combobox displays Technical and product support; the same three required fields and Next step button remain visible; the URL is unchanged.
    screenshot: null
  - evidence_class: observed
    url: https://www.figma.com/contact/
    page_title: "Contact Us | Figma"
    viewport: 1512x727
    browser: Chrome for Testing 151.0.7922.34
    captured_at: "2026-10-08"
    tool: Playwright CLI 0.1.22
    reproduction: In a fresh temporary browser context, load /contact/, choose Do not allow cookies, open Which topic best fits your needs?, and select Technical and product support. Do not enter contact details or click Next step.
    before: The topic combobox is empty; First Name, Last Name, and Work Email Address are required.
    after: The topic combobox displays Technical and product support; the same required fields and Next step remain visible; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

No contact details were entered and Next step was not activated. The selected state and unchanged fields were reproduced in a second browser tool; whether the topic selection changes the next step or routes the request remains unknown.

A later fresh snapshot at the same URL showed a different Contact Us form layout; see the [full-form page map](../../corpus/figma/contact-page-inventory.md). The cause of the difference is unknown, so this observation describes only the Step 1 of 2 state.
