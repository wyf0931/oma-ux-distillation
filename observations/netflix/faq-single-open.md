---
record_type: observation
site: Netflix
page: Singapore landing page FAQ
context: The FAQ answer for “什么是 Netflix？” (What is Netflix?) is expanded and visible.
trigger: explicit activation of a second FAQ question while an answer is open
action: Activate “Netflix 如何收费？” (How does Netflix charge?).
response:
  - The pricing question enters an expanded state and its answer appears inline.
  - The previously expanded “什么是 Netflix？” question collapses and its answer is no longer visible.
  - The current page remains loaded at the same URL.
state: The single expanded FAQ item changes from “What is Netflix?” to “How does Netflix charge?”.
intent: view the pricing answer
purpose: "hypothesis — keep one answer open at a time while visitors browse pricing questions"
evidence:
  - evidence_class: observed
    url: https://www.netflix.com/sg-zh/
    page_title: Netflix 新加坡 — 在线观看电影和电视节目
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open “什么是 Netflix？”; then activate “Netflix 如何收费？” and inspect both question states and answer regions in a fresh snapshot.
    before: “什么是 Netflix？” is expanded with its answer visible; the pricing question is collapsed.
    after: The pricing question is expanded with its answer visible; “什么是 Netflix？” is collapsed and its answer region is absent; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

This observation shows a single-open variant in this Netflix FAQ section. It does not establish whether every Netflix FAQ uses the same behavior.
