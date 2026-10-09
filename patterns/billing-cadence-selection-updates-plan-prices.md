---
record_type: pattern
status: validated
name: Billing Cadence Selection Updates Plan Prices
definition: Selecting a billing cadence on a subscription pricing page updates the displayed recurring prices for the plans to which that cadence applies, while preserving the pricing context.
problem:
  - Visitors need to compare plan costs under different billing cadences.
mechanism: Reflect the chosen monthly or annual cadence in the plan price display without navigating away from the pricing page.
trigger:
  - A pricing page offers more than one billing cadence for a plan.
action:
  - Select a different billing cadence.
response:
  - The selected cadence is reflected in the control state.
  - Applicable plan prices update in place.
  - The visitor remains on the pricing page.
use_when:
  - Subscription plans have different rates for monthly and annual payment.
avoid_when:
  - Pricing is usage-based or fixed to one cadence and no alternate recurring price applies.
variants:
  - Global monthly/yearly choice updates multiple paid plan cards (Notion).
  - Repeated plan-card checkboxes stay synchronized when monthly/yearly mode changes (Linear).
  - A Professional-plan toggle changes seat prices while other plans remain annual-only (Figma).
examples:
  - Notion
  - Linear
  - Figma
evidence:
  - ../observations/notion/pricing-payment-mode-updates-plan-prices.md
  - ../observations/linear/pricing-billing-mode-updates-prices.md
  - ../observations/figma/pricing-professional-plan-monthly-toggle.md
boundaries:
  - ../observations/figma/pricing-professional-plan-monthly-toggle.md
counterexamples: []
confidence: high
---

## Cross-site invariant

Across Notion, Linear, and Figma, changing billing cadence updated the visible price for applicable subscription plans in place while the pricing page remained open. Notion uses one page-wide monthly/yearly choice, Linear displays synchronized billed-yearly checkboxes on Basic and Business, and Figma exposes a toggle on the Professional plan only.

## Boundaries and counterexamples

Figma's Organization and Enterprise plans are labeled annual-only and do not change when the Professional toggle is switched to monthly. These plans are outside the selector's scope, rather than counterexamples to a control that is not offered for them. No direct counterexample has been observed.

## Validation limits

This pattern is supported by three public pricing pages. The displayed prices are capture-time information. No signup, checkout, billing, or plan-change flow was entered, so only the visible quote changed; actual invoice behavior was not tested.
