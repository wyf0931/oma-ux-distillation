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
## Cross-site invariant

Across Mistral, Notion, Airbnb, and Netflix, selecting another language changed page content and locale routing while retaining the same content destination: Mistral's Research page, Notion's Pricing page, Airbnb's Experiences page, and Netflix's Tudum homepage. Mistral also preserved the homepage when switching language.

## Boundaries and counterexamples

This pattern covers language selection, including language/region options that resolve to a corresponding translated page. A market-only selection may behave differently: Apple routed from its US iPhone overview to the UK homepage rather than `/uk/iphone/`. Porsche's country selector changed Singapore homepage to France homepage; only homepage-to-homepage behavior was observed there.

## Validation limits

The pattern has four independent site examples. Persistence across visits, missing translations, and language changes initiated from other content types remain untested. Market routing is represented as a boundary, not part of the invariant.
