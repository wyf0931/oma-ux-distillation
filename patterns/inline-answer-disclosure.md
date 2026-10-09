---
record_type: pattern
status: validated
name: Inline Answer Disclosure
definition: Activating a collapsed question reveals its associated answer in the current page context.
problem:
- Visitors need an answer without leaving the question list.
mechanism: Activate a question control to reveal its associated answer in place.
trigger:
- A question with a collapsed answer is visible.
action:
- Activate the question.
response:
- The question enters an expanded state.
- Its associated answer becomes visible in the current page.
use_when:
- Visitors benefit from reading supporting answers without leaving the question list.
avoid_when:
- The response requires a separate task or destination rather than an inline answer.
variants:
- 'Multiple answers remain open simultaneously: Stripe, Notion.'
- 'Opening a second answer closes the previously open answer: Netflix.'
examples:
- Netflix
- Stripe
- Notion
evidence:
- ../observations/netflix/faq-pricing-disclosure.md
- ../observations/netflix/faq-single-open.md
- ../observations/stripe/pricing-faq-inline-answer.md
- ../observations/stripe/pricing-faq-multiple-open.md
- ../observations/notion/pricing-faq-inline-answer.md
- ../observations/notion/pricing-faq-multiple-open.md
confidence: high
boundaries:
  - ../observations/notion/product-navigation-menu.md
  - ../observations/nvidia/ai-quick-links-disclosure.md
counterexamples: []
---
## Cross-site invariant

Across Netflix, Stripe, and Notion, activating a collapsed pricing FAQ question revealed the associated answer in the current page context. Stripe and Notion allowed two answers to remain open simultaneously; Netflix closed the first answer when a second question was opened.

## Boundaries and counterexamples

This pattern covers question-to-answer disclosure in FAQ sections. Notion's Product menu and NVIDIA's Quick Links control reveal destination links rather than answers; these are adjacent disclosure mechanisms, not instances. No direct counterexample occurred in the three observed FAQ sections; other FAQ implementations remain untested.

## Validation limits

Multi-open behavior was directly observed on Stripe and Notion; Netflix allowed only one open answer in the tested section. Keyboard operation, focus behavior, and long-answer accessibility were not systematically checked.
