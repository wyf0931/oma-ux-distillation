---
record_type: observation
site: Amazon
page: US homepage search
context: "The search header is in its initial state: All Departments is selected and the query is empty."
trigger: explicit selection in the department selector
action: Select Electronics in the department selector.
response:
  - The selector value changes to Electronics.
  - The Electronics option becomes selected.
  - The search field remains empty and focused; no results page opens.
state: search scope changes from All Departments to Electronics while the current page remains open.
intent: narrow a future query to electronics
purpose: "hypothesis — let shoppers constrain search to a department before entering a query"
evidence:
  - evidence_class: observed
    url: https://www.amazon.com/
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the homepage in a clean context and select Electronics from the department combobox; do not enter or submit a query.
    before: The department combobox shows All Departments; the search field is empty.
    after: The department combobox shows Electronics and marks the Electronics option selected; the page URL is unchanged and the query remains empty.
    screenshot: null
confidence: medium
---

## Notes

The department choice was tested without submitting a search. The effect on a later result set was not tested.
