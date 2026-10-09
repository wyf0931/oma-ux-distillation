---
record_type: observation
site: IKEA
page: Global homepage slideshow
context: The public homepage is open; the slideshow control is labeled Pause slideshow of people in their homes with colourful transition, while its associated video element reports paused at 0 seconds.
trigger: a Pause-labelled slideshow control is visible
action: Activate Pause slideshow of people in their homes with colourful transition.
response:
  - The control label changes from Pause slideshow to Play slideshow.
  - The video element in the same video container changes from paused to playing.
  - After approximately 3.5 seconds, the video currentTime is 3.47 seconds; the page URL is unchanged.
state: Activating the Pause-labelled control changes its label to Play while the associated video begins playback.
intent: pause the slideshow motion
purpose: "hypothesis — the control toggles slideshow playback, but the observed media direction did not match its pre-action label"
evidence:
  - evidence_class: observed
    url: https://www.ikea.com/
    page_title: "Hej! Welcome to IKEA Global"
    viewport: 1512x727
    browser: Chrome for Testing 151.0.7922.34
    captured_at: "2026-10-08"
    tool: Playwright CLI 0.1.22
    reproduction: Open the public homepage in an isolated temporary context, choose Do not allow cookies if prompted, and activate the Pause slideshow control. Do not sign in or submit any data.
    before: The control is labeled Pause slideshow; the video element in the same video container is paused at currentTime 0.
    after: The control is labeled Play slideshow; the video element is playing and currentTime advances to about 3.47 seconds after approximately 3.5 seconds.
    screenshot: null
confidence: medium
---

## Notes

The control and video were in the same video-container component. The video being paused at the start means automatic motion before the click was not confirmed; this record is a boundary, not a positive example or direct counterexample.
