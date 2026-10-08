---
site: DuckDuckGo / Duck.ai
page: Search homepage to AI chat
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + fill + click
evidence_class: observed
---

# Search query can be routed into Duck.ai

## Context

URL: https://duckduckgo.com/. The search field already contains `running shoes`, and its action list exposes Search and Ask Duck.ai. The query action list itself is recorded separately in `search-query-action-list.md`.

## Interaction

```yaml
trigger: query action selection
user_intent: continue exploring a query with an AI assistant
user_action:
  - choose Ask Duck.ai
system_response:
  - the browser navigates to Duck.ai chat
  - the query appears as the prefilled user prompt
  - a privacy / terms notice appears before chat input is enabled
state_change: search view changes to a chat view with the query carried over
feedback: the prompt is shown in chat history and the editor
animation: unknown
purpose_hypothesis: offer a conversational path from a search query
```

## Evidence

- Reproduction: open the URL; fill `running shoes`; choose Ask Duck.ai from the query action list.
- Result: the browser navigated to `duck.ai/chat` with `running shoes` in the query parameter and prompt. The page showed a Terms / Privacy notice and a Continue button; the message editor was disabled until Continue.
- Screenshot: not captured.
- Notes / limits: Continue was not clicked because the notice states that proceeding accepts the service's Privacy Policy and Terms. No AI response was requested.
