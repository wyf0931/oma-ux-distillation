---
record_type: pattern
status: validated
name: User-Controlled Automatic Motion
definition: Content that advances or plays without continuous user input exposes a control that lets the user pause it and
  signals how to resume.
problem:
- Automatically moving content can advance before the user finishes reading.
- Background playback can distract from other page content.
mechanism: Pair automatically advancing or playing content with an explicit control that pauses the motion and communicates
  how to resume it.
trigger:
- Automatic slide progression or video playback.
action:
- The user activates a pause control and can later resume the content.
response:
- The automatic motion stops at the current position.
- The control changes to a resume or play action.
use_when:
- A carousel advances on a timer.
- A hero video plays automatically.
avoid_when:
- Motion starts only after an explicit user play action.
- The content is static or has no ongoing playback state.
variants:
- 'Pause / Resume automatic slideshow: Nike.'
- 'Pause / Play hero video: Porsche.'
- 'Pause / Play product-demo animation: GitHub.'
- 'Scroll-triggered highlights gallery with pause control: Apple.'
- 'Pause / Play automatically playing hero video: IKEA.'
examples:
- GitHub
- Nike
- Porsche
- Apple
- IKEA
evidence:
- ../observations/github/feature-demo-animation-pause.md
- ../observations/github/feature-demo-resume.md
- ../observations/nike/homepage-hero-autoplay.md
- ../observations/nike/homepage-hero-pause-autoplay.md
- ../observations/porsche/homepage-video-pause.md
- ../observations/apple/highlights-gallery-autoplay-on-scroll.md
- ../observations/apple/highlights-gallery-pause-stops-motion.md
- ../observations/ikea/homepage-hero-video-pause-control.md
confidence: high
boundaries:
  - ../observations/apple/hero-gallery-pause.md
  - ../observations/ikea/homepage-slideshow-pause-control.md
counterexamples: []
---
# Candidate: user-controlled automatic motion

**Status:** first promoted to [User-Controlled Automatic Motion](../patterns/user-controlled-automatic-motion.md) after pause behavior was observed on three independent sites; later Apple and IKEA evidence extend it to five independent sites.

## Hypothesis

When a featured media region advances or plays automatically, an explicit pause control lets the user stop its motion. The Nike slideshow and Porsche hero video appear related, but the content and control semantics differ, so the shared invariant needs more examples.

## Supporting observations

- [Nike: autoplay pause control](../observations/nike/homepage-hero-pause-autoplay.md) — pausing changed the control label to Resume and the current slide stayed stable during the observed interval.
- [Porsche: hero video pause](../observations/porsche/homepage-video-pause.md) — the control changed from Pause Video to Play Video.
- [GitHub: feature-demo pause](../observations/github/feature-demo-animation-pause.md) — the control changed from Pause to Play.
- [GitHub: feature-demo resume](../observations/github/feature-demo-resume.md) — the control changed from Play back to Pause.
- [Apple: highlights autoplay on scroll](../observations/apple/highlights-gallery-autoplay-on-scroll.md) — the gallery began advancing when scrolled into view without clicking Play.
- [Apple: highlights gallery pause](../observations/apple/highlights-gallery-pause-stops-motion.md) — Pause changed to Play; the selected slide stayed stable over the following four seconds.
- [IKEA: top hero video pause](../observations/ikea/homepage-hero-video-pause-control.md) — a video was already playing on page load with a Pause video control; activating it changed the label to Play video and the video stayed paused.

## Validation questions

- Does the control pause all automatic motion or only one media element?
- Does it preserve position and let users resume from the same place?
- What alternatives exist for reduced motion, keyboard use, and touch?
- Find examples with no pause control and inspect whether the content changes on a timer.
- IKEA's homepage displayed a Pause-labelled slideshow control while the associated video element was paused; activation changed the label to Play and began video playback. The initial autoplay state is unresolved, so this is a boundary, not an instance or direct counterexample.

## Validation outcome

Automatic motion with a pause/play control was directly observed on Nike, Porsche, GitHub, Apple, and IKEA. Apple's separate hero-gallery play control remains outside the pattern because it requires an explicit start. IKEA's distinct lower slideshow control is still a boundary because its associated video began playing after the Pause-labelled control was clicked.
