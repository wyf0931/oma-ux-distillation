# UX Distillation

This repository builds an evidence dataset from real product interactions. The two core reusable outputs are the **UX Distillation Spec** and the **UX Extraction Skill**; the corpus and pattern library ground them in observed behavior.

## Research sequence

```text
site → page or flow → user action → system response → observation
     → candidate pattern → cross site validation → UX pattern
```

Observations describe visible behavior. Hypotheses and intent belong in a separate interpretation field. One site can support an observation or candidate, but cannot validate a reusable pattern by itself.

## Repository map

- `corpus/` — target sites, metadata, and batch status.
- `observations/` — one concrete interaction per file, using the template.
- `candidates/` — hypothesis and promotion records that preserve how patterns were compared.
- `patterns/` — only validated, evidence linked patterns.
- `taxonomy/` — reserved until enough patterns exist to reveal useful clusters.
- `research/` — batch log and repeatable capture protocol.
- [`UX-SPEC.md`](UX-SPEC.md) — draft record and promotion contract, informed by the local `design.md` reference.
- `ux-extractor/SKILL.md` — next deliverable; to be written from the reviewed Spec.

## Current progress

See [the corpus catalog](corpus/README.md) and [research log](research/README.md). The active corpus contains 20 sites, with 25 interaction observations, five page maps, and four cross-site patterns. OpenAI and Perplexity are deferred after human-verification challenges; Mistral AI and DuckDuckGo / Duck.ai are the documented substitutes. The UX Spec is in draft review; the Extraction Skill has not been authored yet.

## Add an observation

The existing [`observations/_template.md`](observations/_template.md) is the initial capture format. `UX-SPEC.md` is a draft for the machine-readable record format; after review, the template and historical records will be aligned to it. Until then, preserve source URLs, action/response, reproduction steps, capture date, and tool, and mark uncertainty explicitly.

## Promotion rule

A candidate can move into `patterns/` only after independent examples from at least two sites show the same interaction invariant. Record supporting cases and counterexamples; retain meaningful differences as variants only when the invariant still holds. Keep the abstraction falsifiable and small.

Confirmed patterns: [Expanded Primary Navigation](patterns/expanded-primary-navigation.md), [Selectable Featured Content](patterns/selectable-featured-content.md), [Query-Guided Search Assistance](patterns/query-guided-search-assistance.md), and [User-Controlled Automatic Motion](patterns/user-controlled-automatic-motion.md). Promoted candidate records remain in `candidates/` for traceability.

The eventual UX token / grammar format will be derived from the validated library rather than decided in advance.
