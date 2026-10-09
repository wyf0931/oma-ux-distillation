---
record_type: observation
site: Tesla
page: Model Y configurator
context: "Model Y configurator initially shows Rear-Wheel Drive selected, with Finance active and the default Stealth Grey exterior."
trigger: "The visitor compares drivetrain options in the Model Y configuration section."
action: "Select All-Wheel Drive."
response:
  - "The All-Wheel Drive option becomes selected while Rear-Wheel Drive is deselected."
  - "The vehicle image description changes from Rear-Wheel Drive Edition to All-Wheel Drive Edition."
  - "The displayed EPA-estimated range changes from 321 mi to 294 mi; 0–60 mph changes from 6.8 sec to 4.6 sec; top speed remains 125 mph."
  - "The estimated finance payment changes from $569/mo to $598/mo."
  - "The configuration summary updates to All-Wheel Drive."
state: "Drivetrain changes from Rear-Wheel Drive to All-Wheel Drive; related specifications, vehicle image, payment estimate, and summary update in place. The URL remains unchanged."
intent: "Compare the All-Wheel Drive configuration with the default Rear-Wheel Drive option."
purpose: "hypothesis — expose the tradeoffs of a configuration choice without leaving the configurator."
evidence:
  - evidence_class: observed
    url: https://www.tesla.com/modely/design#overview
    page_title: "Design Your Model Y | Tesla"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the Model Y design page in an isolated context, dismiss the locale dialog, then select All-Wheel Drive under the Model Y drivetrain options."
    before: "Rear-Wheel Drive is selected. The page shows 321 mi estimated range, 6.8 sec 0–60 mph, 125 mph top speed, $569/mo estimated financing, and a Rear-Wheel Drive vehicle image description."
    after: "All-Wheel Drive is selected. The page shows 294 mi estimated range, 4.6 sec 0–60 mph, 125 mph top speed, $598/mo estimated financing, and an All-Wheel Drive vehicle image description. The summary reflects the new selection; the URL remains the same. No delivery ZIP was entered and Order Now was not activated."
    screenshot: null
confidence: high
---

## Notes

This is a single-session observation of an in-place configuration update. The displayed payment values depend on current pricing and financing assumptions; they are captured only to describe the observed response, not as stable product facts. No order or financing flow was started.
