---
record_type: observation
site: Mistral AI
page: Latest news article search
context: The Latest news listing shows 89 articles across several categories; the Find an article about… field is empty.
trigger: text entry in the article-search field
action: Enter “Mistral Large 4” in Find an article about… without submitting.
response:
  - The URL gains `?search=Mistral+Large+4` while the visitor remains on Latest news.
  - The displayed total changes from 89 articles to 1 article.
  - The only visible article card is “Introducing Mistral Large 4,” labeled RESEARCH.
state: The unfiltered article list changes to one query-matching article while the query remains in the field.
intent: find the Mistral Large 4 article
purpose: "hypothesis — let visitors narrow editorial content as they enter a query"
evidence:
  - evidence_class: observed
    url: https://mistral.ai/news/
    page_title: Latest news | Mistral
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open Latest news with no category selected, note the 89-article mixed-category list, then type “Mistral Large 4” in the article-search field. Do not submit a form or open an article.
    before: The URL is https://mistral.ai/news/; the search field is empty, all category filters are unchecked, the page reports 89 articles, and the first page includes multiple categories.
    after: The URL is https://mistral.ai/news/?search=Mistral+Large+4; the field retains the query, the page reports 1 article, and the only visible card is “Introducing Mistral Large 4” under RESEARCH.
    screenshot: null
confidence: high
---

## Notes

The filtered result appeared before a separate submit action; no submit control was activated. No article was opened.
