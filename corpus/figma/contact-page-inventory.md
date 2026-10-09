---
record_type: page_map
site: Figma
page: Contact Us — full sales form snapshot
visible_structure:
  - The page separates a Talk to a member of our sales team section from a Get product or account support section with a Get support link.
  - The Contact sales form shows required Work email address, First name, Last name, Company name, topic, and plan fields; Phone number is optional; How can we help you? is a multiline field.
  - The form has a Submit button and separate links to the Terms of Service and Privacy Policy.
  - The page includes a Visit our Support Hub link within the form and a separate Get support link above it.
interaction_candidates:
  - Compare the plan selector options without entering contact details or submitting the form.
  - Inspect the separate support links only if their destination behavior is needed for the routing candidate.
limits:
  - No fields were filled and the form was not submitted.
  - Selecting Billing and invoicing changed the topic value but left the visible contact fields unchanged; see the related observation. The plan selector and later routing remain untested.
  - An earlier capture at the same URL showed a Step 1 of 2 form with a topic selector and Next step; the reason for the different page state is unknown.
related_observations:
  - ../../observations/figma/contact-topic-selection-step-one.md
  - ../../observations/figma/contact-topic-selection-full-form.md
evidence:
  - evidence_class: page-evidence
    url: https://www.figma.com/contact/
    page_title: "Contact Us | Figma"
    viewport: 1512x727
    browser: Chrome 154.0.0.0
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP accessibility snapshot
---

## Notes

This map captures the full sales form layout and separate support destinations. An earlier and later isolated browser capture at this URL showed a Step 1 of 2 form; no user action was observed to cause the layout difference, so treat the snapshots as different page states.
