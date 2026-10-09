# UX Extraction Skill evaluation

This is a small, exploratory evaluation of `ux-extractor/SKILL.md` against `UX-SPEC.md` and the project contract. It is not a statistical benchmark; runs are single samples, and the browser environment was intermittent.

## Evaluation tasks

1. **Page map without interaction** — inspect the initial IKEA sofas listing state only; produce `page_map` evidence and keep untested behavior in `interaction_candidates`.
2. **Candidate evidence audit** — classify direct support, boundaries, and counterexamples for `Zero-Count Facet Options Are Disabled` and decide whether the candidate can be promoted.
3. **One interaction observation** — select the visible `Red (1)` facet once on IKEA's price-filtered sofas listing and record before/after evidence.

## Findings

- The initial Skill page map captured useful structure but used `site: IKEA US`; the canonical corpus name is `IKEA`. The Skill now says to copy the exact site identity from `corpus/<site>/site.md` and keep locale in `page` or `context`. A follow-up page map uses `site: IKEA`.
- Skill and baseline candidate audits both correctly keep the zero-count-disabled candidate unvalidated: IKEA is the only direct support site; eBay, Amazon, and Airbnb are boundary or adjacent cases; no direct counterexample was observed.
- The Skill-run IKEA interaction observation records one action, the visible 33-to-1 result change, pressed filter state, URL, and browser provenance. The no-Skill interaction baseline could not load the page in repeated attempts, so that comparison is inconclusive.
- The isolated browser attempts failed intermittently. A parent-assisted page map used a fresh Chrome DevTools MCP tab after checking the public header was logged out; its notes disclose that the tab was not isolated. The baseline page map succeeded in an isolated Playwright session in a later run.
- A full Draft 2020-12 validation passed with zero errors for 163 current observations, two current page maps, 39 pattern/candidate records, one principle, and 23 site records. This validation also caught two unquoted YAML `counterexamples` strings; both are fixed.
- Timing and token data were not exposed by the orchestration tool and are omitted from the benchmarks. Pass rates are descriptive only, not evidence of a broad performance improvement.

## Review

Open [the static evaluation viewer](skill-review.html) to compare the most recent page-map outputs, prior runs, and pass-rate summaries. The iteration files and grading evidence are under `iteration-1/` and `iteration-2/`.

UX-SPEC 0.1.0 is now stable. The Skill is aligned with it and has been evaluated on page-map capture, candidate classification, and a single browser-observed interaction. No-Skill browser capture for the interaction task remains inconclusive because the available browser sessions failed to start reliably; the evaluation notes keep that limitation explicit.
