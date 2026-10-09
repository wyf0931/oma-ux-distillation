---
record_type: observation
site: Anthropic
page: Economic Scenarios explorer, Capabilities question
context: The scenario explorer is on question 1 of 5; the Capabilities slider is at 48 of 100 with a corresponding heatmap and task example.
trigger: explicit adjustment of a model input
action: Focus the Capabilities slider and press ArrowRight once.
response:
  - The slider value changes from 0.48 to 0.505 and the displayed score changes from 48 to 51 of 100.
  - The task example updates to “Draft and negotiate a routine commercial contract”.
  - The tasks-capable heatmap updates to reflect the adjusted value.
  - The page URL remains unchanged.
state: A model assumption changes from 48 to 51 of 100 and the associated scenario outputs update in place.
intent: explore how a small change in AI capability affects projected tasks
purpose: "hypothesis — make a model assumption manipulable and show its projected implications immediately"
evidence:
  - evidence_class: observed
    url: https://www.anthropic.com/institute/econ-scenarios
    page_title: Scenarios for our Economic Future \\ Anthropic
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public scenario explorer, inspect the initial Capabilities value, focus the slider, and press ArrowRight once. Do not advance to the next question.
    before: The Capabilities slider is at 0.48 (48 of 100); its task heatmap and example are visible.
    after: The slider is at 0.505 (51 of 100); the example task and heatmap update; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The slider value was a temporary test input used only to inspect the model's response. No next-question, survey-submit, account, or personal-information action was taken.
