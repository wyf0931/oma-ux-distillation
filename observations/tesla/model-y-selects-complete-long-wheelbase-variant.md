---
record_type: observation
site: Tesla
page: Model Y configurator
context: "The Model Y Rear-Wheel Drive variant is selected, Finance is active, and Stealth Grey is the default exterior. The model list also shows Model Y Premium, Model Y L, and Model Y Performance."
trigger: "The visitor compares another Model Y model variant in the configurator."
action: "Select Model Y L."
response:
  - "Model Y L becomes the selected model variant."
  - "The vehicle image description changes to Front View of Model Y L Premium All-Wheel Drive - Launch Series Edition."
  - "The displayed range changes from 321 mi to 332 mi, acceleration changes from 6.8 sec to 4.4 sec, and top speed remains 125 mph."
  - "The estimated finance payment changes from $569/mo to $1,001/mo, and the summary identifies Model Y L, Long Wheelbase, All-Wheel Drive."
  - "The URL remains unchanged. Model Y L is presented as a complete Long Wheelbase, All-Wheel Drive variant and has no separate drivetrain radio option."
state: "The selected build changes from Model Y Rear-Wheel Drive to the complete Model Y L Long Wheelbase All-Wheel Drive variant, with its image description, specifications, price estimate, and summary updated in place."
intent: "Compare the long-wheelbase Model Y configuration with the standard Rear-Wheel Drive model."
purpose: "hypothesis — show the effect and cost of choosing a different vehicle variant before continuing."
evidence:
  - evidence_class: observed
    url: https://www.tesla.com/modely/design#overview
    page_title: "Design Your Model Y | Tesla"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open the public Model Y design page in an isolated context, reject optional cookies, close the locale dialog, then select Model Y L in the model list. Do not enter a delivery ZIP or activate Order Now."
    before: "Model Y Rear-Wheel Drive is selected. The page shows 321 mi estimated range, 125 mph top speed, 6.8 sec 0–60 mph, and $569/mo estimated financing."
    after: "Model Y L is selected. The image description identifies the Model Y L Premium All-Wheel Drive Launch Series Edition; the page shows 332 mi, 125 mph, 4.4 sec, and $1,001/mo. The summary says Long Wheelbase, All-Wheel Drive; the URL is unchanged."
    screenshot: null
confidence: high
---

## Notes

Unlike the standard Model Y and Model Y Premium groups, which expose separate Rear-Wheel Drive and All-Wheel Drive choices, Model Y L is presented as one complete Long Wheelbase All-Wheel Drive variant. This changes the selected build and preview but does not show an upstream filter that recomputes a separate child option list.
