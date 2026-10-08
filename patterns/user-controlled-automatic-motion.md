# User-Controlled Automatic Motion

```yaml
name: User-Controlled Automatic Motion
definition: >
  Content that advances or plays without continuous user input exposes a control
  that lets the user pause it and signals how to resume.
user_problem:
  - Automatically moving content can advance before the user finishes reading.
  - Background playback can distract from other page content.
trigger:
  - Automatic slide progression or video playback.
interaction:
  - The user activates a pause control and can later resume the content.
system_response:
  - The automatic motion stops at the current position.
  - The control changes to a resume or play action.
purpose:
  - Let the user control the pace of moving content.
when_to_use:
  - A carousel advances on a timer.
  - A hero video plays automatically.
when_not_to_use:
  - Motion starts only after an explicit user play action.
  - The content is static or has no ongoing playback state.
variants:
  - Pause / Resume automatic slideshow: Nike.
  - Pause / Play hero video: Porsche.
  - Pause / Play product-demo animation: GitHub.
examples:
  - GitHub
  - Nike
  - Porsche
evidence:
  - ../observations/github/feature-demo-animation-pause.md
  - ../observations/nike/homepage-hero-autoplay.md
  - ../observations/nike/homepage-hero-pause-autoplay.md
  - ../observations/porsche/homepage-video-pause.md
```

## Cross-site invariant

GitHub's feature-demo control began as Pause and changed to Play after the user action. Nike's carousel changed from Pause to Resume, and its selected slide remained stable during the observed pause interval. Porsche's hero video was already playing on page load; clicking Pause changed its control to Play Video, and read-only video state stayed paused at the same playback time across a three-second interval.

## Boundary cases

The pause affordance is relevant to automatic playback. Apple's `Play Hero gallery` control starts only after an explicit user action; its resulting pause control is documented as a media interaction but is not evidence for automatic motion.

## Validation limits

Resume was not tested. Keyboard, touch, reduced-motion preferences, and the behavior when a user leaves and returns to the page remain untested.
