---
record_type: observation
site: DuckDuckGo / Duck.ai
page: Search results for “running shoes”
context: Web results for “running shoes” are open; the query is visible in the search field and the result-type navigation offers All, Images, Videos, News, and Maps.
trigger: result-type navigation is available above the result list
action: Select Images (图片) from the result-type navigation.
response:
  - The browser navigates to a URL with `ia=images` and `iax=images` while preserving `q=running+shoes`.
  - The Images destination is focused and the result area shows image cards with matching source titles and image descriptions.
  - The search field continues to contain “running shoes”.
state: The web-results view changes to image results while the query remains active.
intent: find images related to the current query
purpose: "hypothesis — let visitors change the result type without re-entering their query"
evidence:
  - evidence_class: observed
    url: https://duckduckgo.com/?ia=web&origin=funnel_home_website&t=h_&q=running+shoes
    page_title: running shoes at DuckDuckGo
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open DuckDuckGo web results for the synthetic query “running shoes”, then select Images (图片) in the result-type navigation.
    before: The URL uses `ia=web`; the search field contains “running shoes”; the result-type navigation offers All, Images, Videos, News, and Maps.
    after: The URL uses `ia=images` and `iax=images`, the search field still contains “running shoes”, and image results are exposed with matching source titles and descriptions.
    screenshot: null
confidence: high
---

## Notes

The page was localized in Chinese during capture. The selected label was 图片 (Images). No image card was opened and no query text was changed.
