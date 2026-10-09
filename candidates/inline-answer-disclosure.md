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
# Candidate: Inline Answer Disclosure

**Status:** promoted to [Inline Answer Disclosure](../patterns/inline-answer-disclosure.md) after replication across three independent sites; retain this file as the hypothesis and validation record.

## Hypothesis

Activating a collapsed FAQ question reveals its associated answer in the current page context, without navigating away.

Possible invariant:

```text
collapsed FAQ question → activate → answer becomes visible in place
```

## Supporting observations

- [Netflix: pricing FAQ disclosure](../observations/netflix/faq-pricing-disclosure.md) — activating a pricing question revealed its answer inline.
- [Stripe: pricing FAQ inline answer](../observations/stripe/pricing-faq-inline-answer.md) — activating a fee question exposed its answer and an associated details link.
- [Stripe: multiple pricing FAQ answers open](../observations/stripe/pricing-faq-multiple-open.md) — activating a second question left the first answer visible, showing a multi-open variant.
- [Notion: pricing FAQ inline answer](../observations/notion/pricing-faq-inline-answer.md) — activating a pricing question revealed its answer in the current page.
- [Notion: multiple pricing FAQ answers open](../observations/notion/pricing-faq-multiple-open.md) — a second answer opened while the first remained visible.

## Validation questions

- **Resolved:** The same question-to-answer transition recurred on Netflix, Stripe, and Notion.
- **Resolved:** Stripe and Notion allow multiple answers to stay open; opening a second Netflix FAQ closes the first.
- Does keyboard operation preserve an understandable expanded state and focus position?
- Are there empty, loading, or navigation-driven variants that need a separate pattern definition?

## Validation outcome

The question → inline answer → current page retained transition was observed on Netflix, Stripe, and Notion. Stripe and Notion allowed multiple answers to remain open; Netflix closed its previous answer when a second question was opened. This is a supported implementation variant, not a counterexample to the core pattern.
