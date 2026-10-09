---
record_type: observation
site: Amazon
page: Customer Service hub
context: "Logged-out Customer Service hub with request categories including orders, Prime, devices, payments, and account help. The page says signing in is needed to get started."
trigger: "The visitor chooses a customer-service request category."
action: "Select ‘Kindle, Fire, Alexa, or other Amazon devices.’"
response:
  - "The browser navigates to Amazon's Sign in page."
  - "The destination asks for a mobile number or email and shows a Continue button."
  - "No request-specific troubleshooting form or destination is visible before sign-in."
state: "The public Customer Service hub is replaced by a Sign in page; the selected category is not reflected in the visible page content."
intent: "Get help with a Kindle, Fire, Alexa, or another Amazon device."
purpose: "hypothesis — require account access before continuing with this support request."
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/gp/help/customer/contact-us
    page_title: "Help & Contact Us - Amazon Customer Service"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the public Customer Service hub in an isolated logged-out context and select ‘Kindle, Fire, Alexa, or other Amazon devices.’"
    before: "The public page presents the selected device-help category alongside other customer-service categories and says signing in is needed to get started."
    after: "The browser navigates to /ap/signin and shows a mobile/email field and Continue. No credentials or other fields are entered. The return route leads back to the customer-service hub; downstream category handling remains unobserved."
    screenshot: null
confidence: high
---

## Notes

This is a logged-out access boundary. The request category is selected, but the post-sign-in response was not observed. It does not establish whether Amazon changes the destination or fields by request type and is not treated as support or a direct counterexample to Request-Type-Driven Contact Routing.
