---
record_type: observation
site: Airbnb
page: Experiences page language selector
context: The Chinese Experiences page is loaded; the language and currency dialog is open with English Singapore available.
trigger: explicit selection of a language and region option
action: Select English Singapore.
response:
  - The browser navigates from `zh.airbnb.com/experiences` to `www.airbnb.com.sg/experiences`.
  - Page title, navigation, and Experiences content switch from Chinese to English.
  - The current page remains the Experiences page.
state: The Experiences page changes from Chinese to English Singapore while retaining the `/experiences` content path.
intent: view Experiences in English for the Singapore region
purpose: "hypothesis — let visitors change language and region without losing the current content destination"
evidence:
  - evidence_class: observed
    url: https://zh.airbnb.com/experiences
    page_title: 爱彼迎体验 - 查找当地人开展的缤纷体验
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the Chinese Experiences page, activate 选择语言, and select English Singapore from the language/region options.
    before: The URL is https://zh.airbnb.com/experiences; the dialog offers language and region options including English Singapore.
    after: The URL is https://www.airbnb.com.sg/experiences; page title and content are in English; the Experiences page remains open.
    screenshot: null
confidence: high
---

## Notes

The destination option changed both language and region. Persistence across visits and switching to other page types were not tested.
