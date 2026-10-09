# UX Distillation Project Contract

## 1. Mission

The repository is an evidence dataset for a reusable UX extraction standard. The long-term product consists of two artifacts:

1. **UX Distillation Spec** — defines what counts as UX evidence, an interaction, a pattern, and eventually a principle.
2. **UX Extraction Skill** — tells an agent how to explore an unfamiliar website and produce evidence that conforms to the Spec.

The research library supports these artifacts. It is not a UX review collection and does not copy visual designs.

The intended sequence is:

```text
Corpus → Observation Library → UX Distillation Spec → UX Extraction Skill
```

Observe first. Extract second. Generalize last.

## 2. Evidence model

The agent must preserve this chain:

```text
Evidence → Observation → Interaction → Intent hypothesis → Pattern → Principle
```

Do not jump from one observed detail to a design principle. Each higher layer must cite the lower layer that supports it.

### L1 — Observation

Record what can be directly seen or reproduced. Keep interpretation out of this layer.

### L2 — Interaction

Normalize an action into its trigger, user action, system response, and state change.

### L3 — Intent

Describe the user problem or purpose as a hypothesis. Keep it separate from observed facts and assign confidence.

### L4 — Pattern

Describe an invariant interaction mechanism found in independent products. A site-specific implementation is an example, not a pattern.

### L5 — Principle

Explain why a pattern is useful only after multiple patterns and counterexamples provide enough evidence.

## 3. Scope

Observe behaviors that affect:

- Navigation and information architecture
- Page and state transitions
- Scrolling, hover, click, drag, swipe, and keyboard interactions
- Search, filtering, sorting, and comparison
- Product discovery and content exploration
- Forms and progressive disclosure
- Feedback, loading, empty states, errors, recovery, and confirmation
- Onboarding and calls to action
- Visual storytelling and animation when they affect interaction or comprehension

Do not extract color, typography, spacing, radius, shadow, CSS, framework, or pixel-level reproduction tokens in this UX research phase. A future UX token layer may compress validated interaction patterns; it must be derived from evidence and kept distinct from visual design tokens.

## 4. Observation schema

One observation file records one user action and its observed response. Use this compact schema:

```yaml
record_type: observation
site:
page:
context:
trigger:
action:
response:
state:
intent:
purpose:
evidence:
confidence:
boundaries: []       # optional: observed non-instances or adjacent cases
counterexamples: []  # optional: same trigger/context, invariant contradicted
```

Use `observations/_template.v1.md` and the matching schemas for all new UX-SPEC 0.1.0 records. They may include capture metadata such as observed date, viewport, browser, tool, and evidence class. The original `_template.md` belongs to historical records and should not be used for new Spec-format observations.

When authoring YAML, quote any string that contains a colon followed by a space, especially list items under `response`. For example, write `- "The page title changes to ‘Amazon.com: Wireless Headphones’."`; otherwise YAML may parse the text after the colon as a mapping instead of a string.

The UX-SPEC defines the persisted record format. Like Google's DESIGN.md, it separates machine-readable YAML from human-readable rationale; unlike a visual design file, it records observed actions, responses, evidence provenance, and clearly marked interpretations. YAML is the normative record structure, but its intent, purpose, problem framing, and usage guidance fields are hypotheses rather than observed facts. Markdown prose explains context and limits but may not strengthen claims beyond the evidence. Keep the shared schema small and preserve site-specific detail in notes or extensions until repeated evidence justifies standardizing it. The first research batches used an earlier template with metadata front matter, a fenced interaction block, and a separate Evidence section. Preserve those records as historical evidence and migrate them only after the Spec is reviewed.

Static page maps are page evidence stored under `corpus/`, not interaction observations. Do not encode them with the observation evidence schema. Use `evidence_class: secondary` only for official documentation that describes behavior not reproduced in the browser; phrase `response` as the documentation's claim, and mark reproduction and before/after as not reproduced or not observed. Secondary evidence establishes what the source says, not current site behavior, and never counts as direct pattern support.

New page maps use `corpus/_page-map-template.v1.md` and `ux-extractor/schemas/page-map.yaml`. Record directly visible structure, possible interactions to test, capture evidence, and limits. Page maps are exploration aids; they do not count as interaction observations or support patterns.

- `context`: page section and initial state.
- `trigger`: what made the interaction available or started it.
- `action`: what the user did.
- `response`: observable system behavior.
- `state`: what changed, stayed the same, or could not be verified.
- `intent`: the user's likely immediate goal; use `unknown` when unclear.
- `purpose`: a separate hypothesis about the design purpose, not direct evidence.
- `evidence`: URL, section, reproduction steps, concise before/after facts, screenshot path when useful, timestamp, and capture tool.
- `confidence`: for observations, confidence in the inferred immediate intent, not confidence that the observed state occurred or in the always-hypothetical purpose. Use low when intent is unknown. For patterns and principles, confidence describes the strength of the cross-record interpretation.

Use `unknown` or `not tested` instead of filling gaps with plausible behavior. An unchanged or blocked state is valid evidence when the action was real and the response was checked.

## 5. Pattern schema

A cross-site validated pattern must contain:

```yaml
record_type: pattern
status: candidate | validated | rejected
name:
definition:
problem:
mechanism:
trigger:
action:
response:
use_when:
avoid_when:
variants:
examples:
evidence:
confidence:
```

Candidate records use the same fields in `candidates/` with `status: candidate`. Start new candidates from `candidates/_template.v1.md`. On promotion, publish a `status: validated` record in `patterns/`, update `patterns/README.md` with its observed support sites and confidence, and update the candidate's structured status to `validated`, preserving its hypothesis and comparison history in the Markdown body.

Retain a rejected candidate with `status: rejected` only when its evidence or comparison history remains useful for future research; do not add rejected records just to fill the library.

The definition describes the reusable interaction logic. `examples` name the sites; `evidence` links to their supporting observation files. `boundaries` link non-instances or adjacent cases; `counterexamples` link cases that directly contradict the stated invariant. Neither counts as support. Variants preserve real differences while keeping the shared mechanism clear.

A pattern needs directly observed instances from at least two independent sites; prefer three or more. `secondary` documentation and page maps may provide context but do not count toward this threshold. Before promotion:

1. Compare the actual action and response, not just similar controls or appearance.
2. State the smallest invariant shared by the examples.
3. Record non-instances and adjacent cases as boundaries; use counterexamples only for cases that match the stated trigger and context but contradict the invariant.
4. Check that the definition could be disproved by a site that does not fit.
5. Keep problem framing, purpose, and usage guidance identifiable as inference when they are not directly observable.

Principles require support from at least two validated patterns; prefer three or more. Start from `taxonomy/_principle-template.v1.md`, store records in `taxonomy/principles/<slug>.md`, link supporting patterns and meaningful boundaries, and state when user outcome evidence is absent. Do not build higher-level taxonomy groups until enough principles exist for useful clusters to emerge.

## 6. Research workflow

Work in batches of approximately five sites.

For each site:

1. Explore a small number of representative journeys: homepage, product or category page, navigation, search/discovery, and an important conversion or support flow when useful.
2. Identify actions with deliberate responses. Ignore decorative effects unless they affect navigation, comprehension, feedback, or user decisions.
3. Capture an initial state, action, and resulting state. Reproduce once when safe.
   For carousels or paginated content, record the active item or visible group before and after; changed Previous / Next enabled states alone do not prove that the content advanced.
4. Save one focused observation per interaction. Keep hypotheses separate from evidence.
5. After a batch, compare observations across sites and create pattern candidates.
6. Promote only after independent examples share a stable interaction invariant; record non-instances as boundaries and consider direct counterexamples separately.

Do not attempt to derive the final UX system after the first batch.

After each active site has an initial pass, choose follow-up journeys from `research/README.md`'s Current research gap. Prioritize observations that could change a candidate's status, direct counterexample checks, and areas with thin coverage. Give each follow-up a concrete question; do not repeat a completed site journey without a replication or validation reason.

## 7. Browser research

Use Chrome DevTools MCP, the connected agent browser, and Playwright when available. Record which tool produced each observation and preserve the original public URL.

Prefer an isolated browser context for public research. Do not record private workspace or account data. If a site is blocked by an access challenge, record the limitation and leave the interaction unobserved; do not bypass the challenge. Do not submit purchases, account creation, personal information, or legally binding terms as part of research.

## 8. Corpus

Start with approximately 20 representative sites spanning different interaction paradigms. The active corpus and per-site status live in `corpus/README.md`. The list may change if a site is inaccessible, unsuitable, or redundant. After the initial pass, add a targeted follow-up site only when an open cross-site question cannot be resolved with the active corpus; record the validation question and reason in the catalog. Do not add a site solely to reach a preferred support count; it must expose a distinct interaction context that can test or challenge the invariant. Preserve the reason for replacements and deferred sites so the corpus remains auditable.

## 9. Repository structure

```text
AGENTS.md
README.md
UX-SPEC.md                     # UX Distillation Spec, after evidence review
ux-extractor/SKILL.md          # agent workflow derived from the Spec
ux-extractor/schemas/          # machine-readable record schemas
corpus/<corpus-slug>/          # metadata and page maps
observations/<corpus-slug>/    # raw interactions, one per file
candidates/                    # unvalidated cross-site hypotheses
patterns/README.md              # flat index with observed support sites and confidence
patterns/<slug>.md              # validated patterns with evidence links
taxonomy/_principle-template.v1.md # template for cross-pattern principles
taxonomy/principles/            # evidence-linked interpretations of multiple validated patterns
research/                      # capture process and batch log
```

The Spec is the schema source of truth. The Skill must consume the Spec rather than define a competing extraction format. Changes to observation or pattern fields must be reflected in the Spec before updating the Skill or migrating the dataset.

File names should describe the interaction, not the interpretation:

```text
observations/apple/hero-product-tab-replacement.md
candidates/query-guided-search-assistance.md
patterns/expanded-primary-navigation.md
```

Use the corpus directory slug for file paths. In observation and page-map front matter, use the exact canonical `site` value from `corpus/<corpus-slug>/site.md`; keep market and locale details in `page`, `context`, or evidence metadata.

Keep each observation or pattern focused and preserve links to evidence.

## 10. Agent behavior

1. Observe before interpreting.
2. Prefer user action → system response descriptions.
3. Separate direct facts, intent hypotheses, and principles.
4. Do not invent patterns to make the library look complete.
5. Do not promote a one-site behavior as reusable.
6. Search for non-instances and potential counterexamples; record non-instances as boundaries and keep variants only when the invariant still holds.
7. Preserve source URLs and reproduction steps.
8. Leave uncertain fields explicit rather than filling them by inference.

## 11. Milestones

The first milestone is a high-quality corpus, focused interaction observations, and a small set of evidence-backed patterns. It is not a complete UX design system.

The Spec and Skill are the two core reusable products. The Spec defines the evidence and abstraction contract; the Skill applies it to websites. A future principle, grammar, or UX token layer must emerge from the validated library rather than be designed in advance.
