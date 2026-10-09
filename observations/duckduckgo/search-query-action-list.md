---
site: DuckDuckGo / Duck.ai
page: Homepage search field
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + fill
evidence_class: observed
---

# Search query opens Search and Ask Duck.ai actions

## Context

URL: https://duckduckgo.com/. The homepage exposed a `利用 DuckDuckGo 进行搜索` combobox.

## Interaction

```yaml
trigger: text entry
user_intent: search for information or explore a topic conversationally
user_action: type "running shoes"
system_response:
  - the query remains in the search combobox
  - a listbox opens with Search and Ask Duck.ai buttons
state_change: empty search field changes to a populated query with a choice list
feedback: two labeled actions appear below the field
animation: unknown
purpose_hypothesis: present different ways to continue from one query
```

## Evidence

- Reproduction: open the URL and fill `running shoes` in the search combobox; do not select an action.
- Result: the snapshot showed a listbox containing Search and Ask Duck.ai.
- Screenshot: not captured.
- Notes / limits: no traditional search was submitted from this state.
