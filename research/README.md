# Research workflow

## Capture protocol

1. Open a representative page in a clean tab and record its URL, title, date, viewport, browser, and automation tool.
2. Choose one interaction journey. Prefer a visible control or user goal over broad site review.
3. Capture the initial state, trigger, and resulting state. Reproduce once when safe; do not submit real purchases, accounts, or personal data.
4. Write the observable response before proposing its purpose. Record disabled, loading, error, empty, or unchanged outcomes too.
5. Save a screenshot when the state transition is hard to describe. Give it a path relative to the observation file.
6. Keep one interaction per observation file. Add candidates only after evidence exists.

## Evidence quality

- **Observed:** directly seen while operating the page, with action and response recorded.
- **Page evidence:** information visible in a snapshot or page content, without a tested state change.
- **Secondary:** official help/documentation describing a behavior that could not be reproduced.

Do not treat page structure, marketing copy, or a screenshot as proof of an interaction response. Preserve exact URLs and distinguish the evidence class.

## Browser tooling

Use Chrome DevTools MCP, the connected agent browser, and Playwright when their sessions are available. Store no cookies, credentials, or browser profile data in this repository. If a tool cannot start, log the concrete error and continue with another available read-only browser surface; do not install a browser or alter a user profile without authorization.

## Batches

Work through the catalog in groups of five. A batch is complete when each site has been explored or explicitly marked inaccessible, and its observed interactions are saved. Only after batches provide cross site evidence should candidate validation begin.

## Progress log

### Batch 1 — Apple, NVIDIA, AMD, Nike, Tesla

Started 2026-10-08. Eight interactions have been captured from Apple, AMD, NVIDIA, Nike, and Tesla in `observations/`. Chrome DevTools MCP initially reported its configured profile was already running, then successfully opened and controlled its own page through `new_page`. The connected agent browser inventory fetch failed. Playwright CLI 0.1.22 is present, but its managed browser is missing; attaching to the user's Chrome failed because remote debugging is not enabled. No browser was installed and no Chrome security setting was changed. Subsequent cross-site comparison promoted four patterns; the pattern and candidate files preserve validation limits.

### Batch 2 — Porsche, Amazon, IKEA, Figma, Linear

Completed 2026-10-08. Four interactions were captured. IKEA's home page and its nine-item designer-story carousel were inspected, but a reliable state change could not be established for the tested slideshow controls; it remains page evidence only. Linear was opened in an isolated DevTools context; only the public product navigation was recorded. No account or workspace content was copied into the library. Nike and Porsche pause controls later supported the User-Controlled Automatic Motion pattern; remaining limits are listed in that pattern file.

### Batch 3 — Stripe, Notion, Mistral AI, Anthropic, DuckDuckGo / Duck.ai

Completed 2026-10-08. Product/research navigation menus were opened on Stripe, Notion, and Anthropic; Mistral's language switcher opened a language list; DuckDuckGo exposed Search and Ask Duck.ai actions for a typed query and carried the query into Duck.ai. The Duck.ai page displayed a Terms / Privacy notice; it was not accepted. OpenAI and Perplexity were moved to the deferred list after Cloudflare human-verification challenges appeared. No verification was attempted.

### Batch 4 — Vercel, GitHub, Netflix, Spotify, Airbnb

Completed 2026-10-08. Six interactions were captured: Vercel product menu expansion, GitHub feature-tab selection, Netflix FAQ disclosure, Spotify search results while typing, and Airbnb date-range and location selection. The GitHub page was loaded in an isolated logged-out context. No account, purchase, or signup flow was entered.

## Cross-site validation — initial pass

Completed 2026-10-08 over the active 20-site corpus. The two blocked initial candidates were replaced under the corpus adjustment rule, and remain listed as deferred. The repository contains 24 individual interaction observations, five page maps, and four promoted patterns supported across two to seven independent sites. Their scope, variants, boundaries, and supporting observation links are documented in `patterns/`. This is an initial validation pass, not a complete UX grammar or token system.
