---
record_type: pattern
status: validated
name: Expanded Primary Navigation
definition: A top-level navigation control opens a menu of related destinations in place, so visitors can inspect routes before
  choosing one.
problem:
- Several related destinations sit beneath one broad product or topic label.
- A visitor needs enough context to choose the right destination.
mechanism: Reveal a set of related destinations from a top-level control while keeping the current page context available.
trigger:
- Activate or hover over an expandable top-level navigation control.
action:
- The visitor opens the menu and selects one destination or dismisses it.
response:
- The control enters an expanded state.
- A set of links appears without changing the current page.
- Some menus group links and add short descriptions.
use_when:
- A top-level topic contains several destinations that visitors may need to compare.
- Group labels or short descriptions help distinguish destinations.
avoid_when:
- A top-level item has one clear destination.
- Users need to scan a long, filterable catalog rather than a small navigation group.
variants:
- 'Grouped product catalog with descriptions: Stripe, Notion, Vercel, Figma.'
- 'Topic menu with direct links: Linear, Anthropic.'
- 'Hover-open vehicle menu with Learn and Order actions: Tesla.'
- 'Keyboard activation moves focus into the revealed destination group: Vercel.'
- 'Modal destination index with expandable model groups: Porsche.'
- 'Tabbed product-category menu with grouped destinations and in-place panel switching: AMD.'
examples:
- Linear
- Stripe
- Notion
- Anthropic
- Vercel
- Figma
- Tesla
- Porsche
- AMD
evidence:
- ../observations/linear/product-navigation-menu.md
- ../observations/stripe/product-navigation-menu.md
- ../observations/notion/product-navigation-menu.md
- ../observations/anthropic/research-navigation-menu.md
- ../observations/vercel/products-menu.md
- ../observations/vercel/products-menu-keyboard-activation.md
- ../observations/figma/products-navigation-menu.md
- ../observations/tesla/vehicles-navigation-menu-hover.md
- ../observations/porsche/navigation-menu-open.md
- ../observations/amd/products-mega-menu.md
- ../observations/amd/products-menu-category-tab.md
confidence: high
boundaries:
- ../observations/vercel/pricing-direct-link.md
counterexamples: []
---
# Candidate: expanded primary navigation

**Status:** first promoted to [Expanded Primary Navigation](../patterns/expanded-primary-navigation.md) after replication across five sites; later evidence extends it to nine independent sites. Retain this file as the hypothesis and validation record.

## Hypothesis

Activating a top-level navigation control reveals a grouped set of related destinations, sometimes with short descriptions, while keeping the visitor on the current page.

This candidate describes the reveal behavior only. It does not assume that every site uses the same menu structure, trigger, or content density.

## Supporting observations

- [Linear Product menu](../observations/linear/product-navigation-menu.md) — Product reveals capability destinations with descriptions.
- [Stripe Product menu](../observations/stripe/product-navigation-menu.md) — Products reveals a catalog with short descriptions.
- [Notion Product menu](../observations/notion/product-navigation-menu.md) — Product reveals capability groups and explanatory copy.
- [Anthropic Research menu](../observations/anthropic/research-navigation-menu.md) — Research reveals topic destinations.
- [Vercel Products menu](../observations/vercel/products-menu.md) — Products reveals grouped destinations under Agent Stack and Core Platform.
- [Vercel keyboard activation](../observations/vercel/products-menu-keyboard-activation.md) — Enter expands Products and moves focus to AI SDK.
- [Figma Products menu](../observations/figma/products-navigation-menu.md) — Products reveals destinations with short descriptions.
- [Tesla Vehicles menu](../observations/tesla/vehicles-navigation-menu-hover.md) — hovering opens vehicle destinations with Learn and Order actions.
- [Porsche navigation modal](../observations/porsche/navigation-menu-open.md) — Menu opens a modal destination index with an expanded Models group.
- [AMD Products mega menu](../observations/amd/products-mega-menu.md) — Products opens tabbed product categories with grouped destinations.
- [AMD Products category switch](../observations/amd/products-menu-category-tab.md) — selecting Graphics replaces the grouped panel without closing the menu or navigating.

## Validation questions

- Does the menu open on click, hover, or keyboard? Keyboard activation is confirmed on Vercel; touch behavior remains untested.
- Are descriptions present because the destination taxonomy is unfamiliar, or are link labels sufficient?
- How do sites keep the menu recoverable after selecting or dismissing an item?
- Look for counterexamples where a top-level item navigates directly or reveals only one destination.
