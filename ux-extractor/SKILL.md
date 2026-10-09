---
name: ux-extractor
description: "Use whenever the user wants a website's interaction patterns distilled into source-linked UX evidence, asks to study user actions and system responses across sites, populate observation/candidate/pattern records, or build a reusable UX pattern library. Follow UX-SPEC.md; prioritize browser-observed interactions and promote patterns only after independent-site validation. Do not use for visual design-token extraction or generic UX reviews."
compatibility: "Website exploration requires a browser surface such as Chrome DevTools MCP, the connected agent browser, or Playwright. Corpus-only comparison and record maintenance can run from repository files without a browser."
---

# UX Extraction Skill

This Skill turns public website research into evidence records for the repository. It follows UX-SPEC.md and AGENTS.md. UX-SPEC.md is the schema source of truth; this Skill must not redefine its fields or evidence thresholds.

This Skill targets stable UX-SPEC version 0.1.0. If the Spec changes, update this Skill and the schema resources together.

## When to use

Use this Skill when the user asks to:

- Study one or more websites for UX interactions.
- Add interaction observations to the corpus.
- Compare interactions across products.
- Create or validate UX pattern candidates.
- Update the evidence-backed UX pattern library.

Do not use it for visual style reviews, CSS extraction, color/typography/spacing tokens, or pixel-level cloning.

## Research scope

Use this coverage guide when choosing journeys; do not force every area onto every site. Look for observable interactions that affect task progress:

- Navigation, information architecture, and page/state transitions.
- Scrolling, hover, click, drag, swipe, and keyboard behavior.
- Search, filtering, sorting, comparison, product discovery, and content exploration.
- Forms, progressive disclosure, onboarding, and calls to action.
- Feedback, loading, empty states, errors, recovery, and confirmation.
- Storytelling or motion only when it changes navigation, comprehension, feedback, or decisions.

Use UX-SPEC.md for the evidence boundary: visual appearance values do not count as UX observations on their own.

## Before browsing

1. Read AGENTS.md and UX-SPEC.md.
2. Read the corpus catalog and the target site record.
3. Read `patterns/README.md`, then review relevant observations, candidates, and pattern records to avoid duplicating evidence.
4. If the user supplies one URL, research that URL. Otherwise, if some active sites have not had an initial pass, process the next batch of about five. Once every active site has an initial pass, read `research/README.md`'s Current research gap and choose a focused follow-up that could resolve an open validation question, test a boundary, or improve a thinly covered site. Do not repeat a completed journey without a replication or validation reason.
5. Use a fresh, isolated browser context where available. Always record the exact page URL, capture date, and automation tool. Record the page title, viewport, and browser when available; use `unknown` when a value cannot be obtained.

When the corpus explicitly adds or replaces a site, create its record from `corpus/_site-template.v1.md`, validate its YAML front matter against `ux-extractor/schemas/site.yaml`, and update the catalog with the replacement reason. A site target is planning metadata, not interaction evidence. Do not add a site merely to manufacture another pattern example.

Use the `site` value from `corpus/<corpus-slug>/site.md` exactly in observations and page maps. Use the corpus directory slug—not the display label—in file paths such as `observations/<corpus-slug>/<action-slug>.md` and `corpus/<corpus-slug>/<page-map>.md`. Put country, market, locale, or subdomain details in `page`, `context`, or evidence metadata; do not create a new site identity for a localized version of the same product.

## Explore and capture

For each site, select a few representative journeys: homepage, product or category page, navigation, search/discovery, and one important support or conversion path when useful. Do not attempt to document every page.

For every meaningful interaction:

1. Capture the initial state using an accessibility snapshot or equivalent browser state.
2. Identify a concrete user action and the control it targets.
3. Perform one safe, reversible action.
4. Capture the resulting state and compare it with the initial state. For carousels or paginated content, record the active item or visible group and any position indicator before and after; a Previous / Next enabled-state change alone does not prove the content advanced.
5. When safe, reproduce the interaction once from an equivalent initial state. Use a fresh page or reverse the change first. Record the repeat as a separate item in the observation's `evidence` list, with its own before/after and reproduction details; note any variation in the Markdown body rather than treating a one-off response as stable. Do not repeat an action that is irreversible, externally committing, or otherwise unsafe.
6. If no response is visible, verify the action actually occurred before recording “none observed.”
7. Save one observation file per interaction under `observations/<corpus-slug>/<action-slug>.md`, using `observations/_template.v1.md`. Name the file for the concrete user action or changed control, not an inferred design intent.

Use the observation and interaction schemas in schemas/. The YAML front matter is machine-readable; the Markdown body explains evidence limits and interpretation. Keep observed facts separate from user-intent and purpose hypotheses. Use unknown when intent cannot be inferred; set observation confidence to low when intent is unknown. Confidence applies to immediate intent on observations, pattern fit on patterns, and cross-pattern rationale on principles; it never upgrades a purpose hypothesis into evidence.

Quote any YAML string containing a colon followed by a space, especially response-list items. After authoring, parse the front matter and confirm values such as `response` are strings or string lists as required by the schema; YAML can otherwise interpret an unquoted colon as a mapping.

Keep the shared schema small. Preserve site-specific details in Markdown notes or an `extensions` object, and do not add shared required fields from a single example. The YAML evidence fields remain normative; prose can explain interpretation and limits but must not overstate the captured behavior.

Use optional observation-level `boundaries` and `counterexamples` as short text notes only when the individual record explicitly documents an adjacent case or a contradiction to an identified candidate/pattern. These annotations do not classify support; the linked pattern record remains the canonical evidence comparison.

Capture screenshots only when the visual change is important and the accessibility or DOM state does not sufficiently describe it. Store screenshots beside the observation and reference them from evidence.

If the page structure is visible but no action was tested, write a page map in `corpus/<corpus-slug>/` using `corpus/_page-map-template.v1.md` and `schemas/page-map.yaml`. Use the canonical corpus `site` label in frontmatter; use the directory slug only in the path. Treat listed controls as interaction candidates, not evidence of a response. A page map cannot support a candidate or validated pattern; create a separate observation after testing an action.

When an action produces no visible result, record the before/after state and how you verified the action occurred. Do not infer failure from a missing suggestion or changed component if the page did not confirm that the intended action was received.

If official documentation describes an interaction that could not be reproduced, label that evidence item `secondary`. Phrase `response` as the documentation's claim, state that reproduction was not performed, and mark before/after as not observed. This evidence establishes what the source says, not current site behavior, and cannot count toward candidate or pattern support.

## Browser tools and access boundaries

Use Chrome DevTools MCP, the connected agent browser, or Playwright when available. Read the tool instructions and obtain a fresh page/snapshot before each interaction. After a browser restart, relist pages and use new page identifiers.

Prefer public, logged-out pages and isolated browser contexts. Do not copy private workspace or account content into the repository. Do not submit purchases, signups, personal information, or legally binding terms. Do not solve or bypass CAPTCHA/human-verification challenges. If a site is blocked, record the limitation and continue with another active corpus site; replacement decisions belong in the corpus catalog.

If a public landing page exposes an authenticated workspace or account dataset in an embedded demo, do not inspect or operate that workspace. Record the access boundary and continue with other public page evidence. An interaction that could not be tested is an access limitation, not a counterexample to a candidate.

For scenario explorers, calculators, or prediction tools, use only a clearly synthetic and reversible input to inspect the local response. Describe it as a test input, never as a participant's belief. Do not submit or save survey answers or personal predictions.

Choose reject-optional or necessary-only cookie options when needed. If a browser profile is locked, retry once or use another available browser surface. Do not close the user's browser, enable remote debugging, install a browser, or alter a profile without authorization.

If one retry and the available fallback surfaces all fail, record the tool limitation in the research log and stop that browser interaction. Do not describe the site as inaccessible, treat an unverified state as a boundary, or infer a response from the tool error. Continue independent repository work and report the unresolved browser setup.

## Create candidates and patterns

After a batch, compare observations across sites:

1. Create a candidate when one or more observations suggest a reusable interaction mechanism. A candidate may begin from one site, but label it as a hypothesis and state what independent examples or counterexamples are still needed. Start from `candidates/_template.v1.md` and use the pattern schema with status candidate.
2. Compare trigger, action, response, and state. Similar-looking controls alone are not evidence of the same pattern.
3. Search for counterexamples and boundaries. Put supporting observations in `evidence`, non-instances and adjacent cases in `boundaries`, and only direct contradictions to the stated invariant in `counterexamples`. None of the latter two count toward the supporting-site threshold. Preserve meaningful implementation differences as variants.
4. Check the five pattern-quality criteria in UX-SPEC.md before promotion: reusable across independent sites, directly observable, semantic rather than visual, minimal, and falsifiable. If a criterion is unclear from the evidence, keep the candidate open or state the limit.
5. Promote to status validated only when directly observed interaction records from at least two independent sites support the same invariant; prefer three or more. For version 0.1.0 records, require `evidence_class: observed` on a supporting item in the `evidence` list. For historical records, accept the original top-level `evidence_class: observed` only when the Markdown `Interaction` and `Evidence` sections document the concrete action, observed result, source URL, and reproduction or capture method. Do not count incomplete historical records, secondary documentation, or page maps. Do not migrate historical files just to make them conform to the current schema. Count unique product/site identities from `corpus/` as defined in UX-SPEC.md: pages, paths, locales, and subdomains for the same product count once. If independence is unclear, count examples together as one site and document any exception. Link every supporting observation, create the validated record in `patterns/`, update `patterns/README.md` with directly observed site identities and confidence, and update the candidate record's status while retaining its comparison history.
6. When evidence directly falsifies a candidate, set its structured status to `rejected`. Retain the rejected record only when its evidence or comparison history can help future research; otherwise, do not keep a rejected record solely to fill the library.
7. Write a principle only when at least two validated patterns support a shared rationale; prefer three or more. Start from `taxonomy/_principle-template.v1.md`, save under `taxonomy/principles/<slug>.md`, and validate against `schemas/principle.yaml`. Link every supporting pattern and the patterns that challenge the scope, and state when the evidence describes interface behavior without user outcome data. Do not add higher-level taxonomy groups or UX-token vocabulary to fill empty sections; derive those later from repeated principle clusters.

Treat `problem`, `use_when`, and `avoid_when` as hypothesis fields, as described in `schemas/pattern.yaml`. Keep them narrow and proportionate to the examples; do not present them as user-research findings unless separate research evidence is linked. Pattern confidence applies to the shared invariant, not every usage recommendation.

One site can produce an observation or candidate, never a validated reusable pattern.

## Finish a batch

Update the site status and research log. Report:

- Sites and journeys explored.
- Observation and page-map files added.
- Candidate, validated-pattern, or principle changes.
- Access blocks and unverified behavior.
- The next research gap.

After the initial corpus pass, log follow-up journeys in the existing site's records and research log; do not treat each follow-up as a new batch of unvisited sites. Keep the question being tested explicit so repeated captures add evidence rather than duplicate it.

Keep the final report concise and evidence-linked.

Before closing the batch, make a consistency pass:

1. Parse each new site target, Spec-format observation, page map, candidate, pattern, and principle front matter with a YAML-aware parser; confirm required fields and field types against `ux-extractor/schemas/` (`site.yaml` validates target metadata, not UX evidence).
2. Check every local evidence link and site name against the corpus entry; resolve principle pattern references from the repository root.
3. For each validated pattern, count independent supporting sites from its evidence links. Apply the Spec's current-format or historical-format direct-observation rule to each record; boundaries, blocked actions, secondary sources, and non-instances do not count as support.
4. Reconcile per-site observation totals with `corpus/README.md`, pattern site counts with the linked direct evidence in `patterns/README.md`, and repository totals with `README.md` and `research/README.md`.
5. Leave historical records in their original format unless a migration is deliberately planned under the Spec.
