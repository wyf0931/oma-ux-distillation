---
record_type: observation
site: Mistral AI
page: Latest news
context: The Latest news listing shows 89 articles and all five category filters are unchecked.
trigger: category filter is available above the article list
action: Select the RESEARCH category filter.
response:
  - The RESEARCH checkbox becomes selected and the URL gains `?categories=research`.
  - The displayed total changes from 89 to 40 articles.
  - The nine article cards visible on the first result page are all labeled RESEARCH.
state: The unfiltered 89-article listing changes to a research-filtered 40-article listing while the visitor remains on Latest news.
intent: browse research articles without unrelated news categories
purpose: "hypothesis — narrow a broad editorial listing by topic"
evidence:
  - evidence_class: observed
    url: https://mistral.ai/news/
    page_title: Latest news | Mistral
    viewport: 1512x727 CSS pixels
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the Latest news page with no category selected, then activate the RESEARCH category filter.
    before: The URL is https://mistral.ai/news/; all five category checkboxes are unchecked, 89 articles are reported, and the first page includes Research, Company, Solutions, and Product cards.
    after: The RESEARCH checkbox is checked, the URL is https://mistral.ai/news/?categories=research, 40 articles are reported, and all nine visible first-page cards are labeled RESEARCH.
    screenshot: null
confidence: high
---

## Notes

The filter was activated through its visible label because the native checkbox input has a 1px hit target. The article cards updated in place after the URL changed. No article was opened and no other category was selected.
