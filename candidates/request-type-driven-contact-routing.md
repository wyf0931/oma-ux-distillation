---
record_type: pattern
status: validated
name: Request-Type-Driven Contact Routing
definition: In a contact flow, a request-type choice determines the fields or destination shown during the current or a later
  step.
problem:
- Visitors may need different teams or information depending on the reason for contacting an organization.
mechanism: Ask for the request type before or during a multi-step flow, then use that choice to reveal tailored fields or
  a relevant help destination.
trigger:
- A public contact page asks the visitor to select a request type.
action:
- Select a request type such as Contact sales, Product support, or Increase rate limits.
response:
- The current or subsequent step shows contact fields that match the selected request.
- A support request may route to a relevant help destination instead of showing the sales form.
use_when:
- Different request types require different information or support destinations.
avoid_when:
- All requests use the same fields and route, making an extra classification step unnecessary.
variants:
- A request type reveals a tailored contact form.
- A request type routes to a support resource.
- A sales choice in a help portal leads to a sales-specific contact form.
examples:
- Anthropic
- Linear
- GitHub
evidence:
- ../observations/anthropic/contact-sales-selection-reveals-form.md
- ../observations/anthropic/contact-sales-product-support-route.md
- ../observations/anthropic/contact-sales-rate-limits-branch.md
- ../observations/linear/contact-hub-sales-routing.md
- ../observations/linear/contact-hub-support-routing.md
- ../observations/github/help-portal-sales-route.md
counterexamples: []
confidence: high
boundaries:
- ../corpus/notion/contact-sales-page-inventory.md
- ../observations/vercel/contact-sales-country-selection.md
- ../observations/figma/contact-topic-selection-step-one.md
- ../observations/figma/contact-topic-selection-full-form.md
- ../observations/nike/help-category-selection-form-unchanged.md
- ../observations/nike/help-track-order-category-selection.md
- ../observations/stripe/contact-sales-country-selection.md
- ../observations/amazon/customer-service-product-support-selection-signin.md
- ../corpus/figma/contact-page-inventory.md
---

# Candidate: Request-Type-Driven Contact Routing

**Status:** promoted to [Request-Type-Driven Contact Routing](../patterns/request-type-driven-contact-routing.md) after direct routing variants were observed on Anthropic, Linear, and GitHub.

## Hypothesis

Asking what a visitor needs before or during a contact flow can reveal only the fields relevant to that request, or route the visitor to a more appropriate support destination, either immediately or in a later step.

Possible invariant:

```text
select request type → reveal a tailored form or route to the relevant help path
```

## Supporting observations

- [Anthropic: Contact sales reveals fields](../observations/anthropic/contact-sales-selection-reveals-form.md) — choosing Contact sales revealed required business-contact fields.
- [Anthropic: Product support handoff](../observations/anthropic/contact-sales-product-support-route.md) — choosing Product support replaced the sales form fields with a Support Center link.
- [Anthropic: Increase rate limits branch](../observations/anthropic/contact-sales-rate-limits-branch.md) — the request type displayed a tailored contact form with an Organization ID requirement and instructions.
- [Linear: Sales contact route](../observations/linear/contact-hub-sales-routing.md) — choosing Sales on the public contact hub opened a dedicated sales form.
- [Linear: Support contact route](../observations/linear/contact-hub-support-routing.md) — choosing Support opened a distinct logged-out support page with login and email paths.
- [GitHub: Help portal Sales route](../observations/github/help-portal-sales-route.md) — choosing GitHub Sales from the public Help portal opened a dedicated Sales page with a tailored form and a separate Enterprise Support link.

## Boundary evidence

- [Notion: Contact Sales page map](../corpus/notion/contact-sales-page-inventory.md) — the visible first step shows a fixed Work email field and Next button; no request-type selector was visible, and later steps were not opened.
- [Vercel: country selection](../observations/vercel/contact-sales-country-selection.md) — changing Country did not alter the form fields; this is not a request-type interaction.
- [Figma: topic selection on Step 1](../observations/figma/contact-topic-selection-step-one.md) — selecting Technical and product support changed the selected value while leaving the required Step 1 fields visible; this was reproduced with Chrome DevTools MCP and Playwright. The next step was not opened, so later routing is unknown. This is not counted as a positive example or counterexample.
- [Figma: full-form topic selection](../observations/figma/contact-topic-selection-full-form.md) — selecting Billing and invoicing changed the topic value but left the visible contact fields unchanged; later routing remains unknown. This is a boundary, not support or a direct counterexample.
- [Nike: support Category selection](../observations/nike/help-category-selection-form-unchanged.md) — selecting Product Info / Support changed the category value but left the visible request fields unchanged; Continue was not activated, so later routing remains unknown. This is a boundary, not support or a direct counterexample.
- [Nike: Track My Order selection](../observations/nike/help-track-order-category-selection.md) — the category value changed while the same fields remained and Continue stayed disabled; later routing is unknown. This is a boundary, not support or a direct counterexample.
- [Stripe: Contact Sales country selection](../observations/stripe/contact-sales-country-selection.md) — selecting France changed the country value while leaving the first-step work email field, Continue button, and URL unchanged; later steps were not opened. Country selection is not request-type routing.
- [Amazon: device support selection](../observations/amazon/customer-service-product-support-selection-signin.md) — selecting device support from the logged-out Customer Service hub opened a generic Sign in page. Post-login handling was not observed, so this does not establish whether Amazon changes the route by request type.
- [GitHub: Contact Us sign-in gate](../observations/github/help-contact-requires-signin.md) — the logged-out Help portal's Contact Us link opened a generic support sign-in page; authenticated handling remains unknown.
- [GitHub: account-recovery reason selection](../observations/github/cannot-sign-in-reason-selection-no-route.md) — selecting No account left the required-email form unchanged and Submit disabled. Later routing after submission remains unobserved.
- [Figma: full-form Contact Us page map](../corpus/figma/contact-page-inventory.md) — a capture at the same URL showed a full sales form and separate support links; the different form state has no verified cause and does not establish request-type-dependent routing.

## Validation questions

- Does this request-type routing recur beyond the three observed products?
- Do other request types reveal tailored forms, direct help links, or another response?
- **Resolved for initial validation:** Anthropic reveals request-specific forms and routes Product support to help; Linear routes Sales and Support choices to dedicated contact destinations; GitHub Help routes a Sales choice to a dedicated form.
- How does the flow preserve entered data when a visitor changes the request type?
- Are required fields announced or marked before submission in each branch?

## Validation outcome

The shared mechanism is that a visitor identifies the kind of help they need and the site directs them to a matching contact path. Anthropic uses an in-place request selector that reveals tailored fields or a support destination; Linear and GitHub use public link-based choices to reach purpose-specific contact pages. These are distinct implementations of the same intent-routing mechanism.
