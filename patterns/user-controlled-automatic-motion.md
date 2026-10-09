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
## Cross-site invariant

GitHub's feature-demo control changed from Pause to Play and back to Pause when activated in each direction. Nike's carousel changed from Pause to Resume, and its selected slide remained stable during the observed pause interval. Porsche's hero video was already playing on page load; clicking Pause changed its control to Play Video, and read-only video state stayed paused at the same playback time across a three-second interval. Apple's Highlights Gallery began advancing when scrolled into view, then changed from Pause to Play after a pause request; the selected item remained stable for four seconds afterward. IKEA's top Xbox hero video was already playing at first inspection with a Pause video control; activating it changed the control to Play video and the video stayed paused.

## Boundary cases

The pause affordance is relevant to automatic playback. Apple's separate `Play Hero gallery` control starts only after an explicit user action; it is outside this pattern. The Highlights Gallery is a distinct region that started automatically when it entered the viewport. IKEA's separate lower slideshow control remained a boundary: its associated video was paused at first inspection, then began playing after the Pause-labelled control was activated. This is distinct from the top Xbox hero video, which was already playing on page load.

## Validation limits

Playback time or animation frames were not measured on GitHub. Apple's gallery selection changed around the pause click; the exact frame at which pausing took effect is unresolved. Automatic advancement was directly observed on Nike and the Apple Highlights Gallery; the hero video was directly inspected on Porsche and IKEA. IKEA's top hero video remained paused during the measured two-second interval, but the pause playhead could not be matched to an immediately adjacent pre-click time sample. Keyboard, touch, reduced-motion preferences, and the behavior when a user leaves and returns to the page remain untested.
