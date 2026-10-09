---
record_type: pattern
status: validated
name: Language Selection Preserves Content Path
definition: Selecting a language changes the current content page to its translated counterpart while retaining the page path
  or content type.
problem:
- Visitors may need another language without losing the content destination they are using.
mechanism: A language or language/region option maps the current page to its localized counterpart.
trigger:
- The visitor selects another language from a language selector.
action:
- Choose a language or language/region option.
response:
- The page language changes.
- The current content path or page type remains.
use_when:
- A translated counterpart exists for the current content destination.
avoid_when:
- A market selection intentionally routes to a different regional landing page and does not map the current destination.
variants:
  - 'Direct language switcher: Mistral.'
  - 'Language/region option: Notion, Airbnb.'
  - 'Locale-prefixed route preserves the Tudum homepage: Netflix.'
examples:
- Mistral AI
- Notion
- Airbnb
- Netflix
evidence:
- ../observations/mistral/language-switcher-select-french.md
- ../observations/mistral/research-page-locale-switch.md
- ../observations/notion/pricing-language-switch.md
- ../observations/airbnb/experiences-language-switch.md
- ../observations/netflix/tudum-language-switch-preserves-home.md
confidence: high
boundaries:
- ../observations/apple/market-selection-uk-homepage.md
- ../observations/porsche/country-selector-select-france.md
counterexamples: []
---
# Candidate: Direct Language Switch Preserves Content Path

**Status:** promoted to [Language Selection Preserves Content Path](../patterns/language-selection-preserves-content-path.md) after replication across three independent sites; retain this file as the hypothesis and validation record.

## Hypothesis

A direct language control changes the current content page to its corresponding translated version while preserving the content path.

Possible invariant:

```text
current content page + direct language selection → translated counterpart at the equivalent content path
```

## Supporting observations

- [Mistral: selecting French on the homepage](../observations/mistral/language-switcher-select-french.md) — the English homepage at `/` changed to the French homepage at `/fr/`.
- [Mistral: switching language on Research](../observations/mistral/research-page-locale-switch.md) — French `/fr/research/` changed to English `/research/`, retaining the Research page.
- [Notion: switching language on Pricing](../observations/notion/pricing-language-switch.md) — English `/pricing` changed to French `/fr/pricing`, retaining the Pricing page.
- [Airbnb: switching language on Experiences](../observations/airbnb/experiences-language-switch.md) — Chinese Experiences changed to English Singapore Experiences, retaining the `/experiences` path.
- [Netflix: switching language on Tudum](../observations/netflix/tudum-language-switch-preserves-home.md) — Portuguese selection changed `/tudum` to `/tudum/pt-br` and translated the Tudum homepage content.

## Boundaries and counterexamples

- [Porsche: France — Français](../observations/porsche/country-selector-select-france.md) — selecting a country/language from the Singapore homepage led to the French homepage.
- [Apple: UK market selection](../observations/apple/market-selection-uk-homepage.md) — selecting the UK market from the US iPhone overview routed to the Apple UK homepage, not `/uk/iphone/`.

These controls combine market and language selection and route through regional destinations. Apple routed from the US iPhone overview to the UK homepage, rather than the equivalent UK iPhone page; it is a boundary for market-only selection.

## Validation questions

- **Resolved:** Notion Pricing and Airbnb Experiences preserve non-homepage content paths on language change.
- When a country offers multiple languages, how is the language choice represented and remembered?
- Do market selectors intentionally return to a regional homepage, or can they preserve the current content path?

## Validation outcome

The same-page-content transition is supported on Mistral, Notion, Airbnb, and Netflix. Netflix's locale segment is a routing variant; market selection can use a different route and remains outside the pattern definition.
