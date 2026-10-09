---
record_type: observation
site: Figma
page: Contact Us Work email field
context: The public Contact Us form is open at step 1; Work email is empty and the form has not been submitted.
trigger: an invalid email value is entered and the field loses focus
action: Enter the synthetic value `not-an-email` in Work email, then press Tab without activating Next step.
response:
  - The Work email field is marked invalid.
  - "An associated description appears: ‘Please provide a valid email address’."
  - The form remains at step 1 and the page URL is unchanged.
state: The empty Work email field changes to an invalid state with explicit correction guidance.
intent: provide a work email for the Contact Us request
purpose: "hypothesis — explain the accepted format before the visitor advances"
evidence:
  - evidence_class: observed
    url: https://www.figma.com/contact/
    page_title: Contact Us | Figma
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: On the public Contact Us form, enter `not-an-email` in Work email and move focus with Tab; do not activate Next step.
    before: Work email is empty; First Name, Last Name, and Next step are visible; the form is on step 1.
    after: Work email contains `not-an-email`, is marked invalid, and exposes “Please provide a valid email address”; step and URL are unchanged.
    screenshot: null
confidence: high
---

## Notes

The email value was synthetic. No name or other contact detail was entered and Next step was not activated.
