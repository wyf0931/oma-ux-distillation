---
record_type: pattern
status: validated
name: Request-Type-Driven Contact Routing
definition: A contact experience asks or lets visitors identify what they need, then directs them to a corresponding form, team, or support destination.
problem:
  - Visitors with different needs may otherwise reach an irrelevant form or team.
mechanism: Match a visitor's stated contact intent to a purpose-specific set of fields or destination.
trigger:
  - A visitor starts from a contact or support entry point.
action:
  - Select or follow the option that best describes the reason for contacting the organization.
response:
  - The site reveals a form tailored to that request or navigates to a relevant contact destination.
use_when:
  - Different contact intents require different information, teams, or support channels.
avoid_when:
  - Every request uses the same form and destination, so categorization would add an unnecessary step.
variants:
  - In-place request selection reveals a tailored form or support link (Anthropic).
  - Contact-hub choices route to dedicated Sales or Support pages (Linear, GitHub).
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
boundaries:
  - ../corpus/notion/contact-sales-page-inventory.md
  - ../observations/vercel/contact-sales-country-selection.md
  - ../observations/figma/contact-topic-selection-step-one.md
  - ../observations/figma/contact-topic-selection-full-form.md
  - ../observations/nike/help-category-selection-form-unchanged.md
  - ../observations/nike/help-track-order-category-selection.md
  - ../observations/stripe/contact-sales-country-selection.md
  - ../observations/amazon/customer-service-product-support-selection-signin.md
  - ../observations/github/help-contact-requires-signin.md
  - ../observations/github/cannot-sign-in-reason-selection-no-route.md
  - ../corpus/figma/contact-page-inventory.md
counterexamples: []
confidence: high
---

## Cross-site invariant

Anthropic, Linear, and GitHub all offer a public choice that directs visitors with a sales or support need to a corresponding contact path. Anthropic uses an in-place request selector that reveals tailored fields or a support destination. Linear uses Sales and Support choices on a contact hub. GitHub's Help portal links to a dedicated sales form and provides a separate support path. The shared invariant is intent selection followed by a matching contact path; the interaction surface and timing differ.

## Boundaries and counterexamples

Country or topic selection alone does not establish request-based routing. On Vercel and Stripe, changing country left the visible contact form and URL unchanged. Figma and Nike category/topic choices left the observed fields unchanged, and their later routing was not established. Notion's page map showed a fixed first step, but no later step was tested. Amazon's device-support category and GitHub Help's Contact Us link led logged-out visitors to generic sign-in pages; the after-login routes remain unknown. GitHub's Unable to sign in form exposed reason choices, but selecting No account left the incomplete form unchanged; the required email prevented submission, so later handling is unknown. These are boundaries or incomplete observations, not direct counterexamples to a confirmed route change.

No direct counterexample has been observed. A direct counterexample would require a matching request choice that leaves the same form and destination in place after the relevant step is observed.

## Validation limits

This pattern is supported by three independent sites and includes in-place branching and link-based routing variants. The GitHub and Linear sales forms were inspected without entering contact details; Linear support offers login or email, while Anthropic offers a Support Center destination. Downstream handling after form submission is unobserved. Search for direct counterexamples and additional non-sales contact journeys.
