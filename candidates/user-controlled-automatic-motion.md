# Candidate: user-controlled automatic motion

**Status:** promoted to [User-Controlled Automatic Motion](../patterns/user-controlled-automatic-motion.md) after pause behavior was observed on three independent sites; retain this file as the hypothesis and validation record.

## Hypothesis

When a featured media region advances or plays automatically, an explicit pause control lets the user stop its motion. The Nike slideshow and Porsche hero video appear related, but the content and control semantics differ, so the shared invariant needs more examples.

## Supporting observations

- [Nike: autoplay pause control](../observations/nike/homepage-hero-pause-autoplay.md) — pausing changed the control label to Resume and the current slide stayed stable during the observed interval.
- [Porsche: hero video pause](../observations/porsche/homepage-video-pause.md) — the control changed from Pause Video to Play Video.
- [GitHub: feature-demo pause](../observations/github/feature-demo-animation-pause.md) — the control changed from Pause to Play.
- [GitHub: feature-demo resume](../observations/github/feature-demo-resume.md) — the control changed from Play back to Pause.

## Validation questions

- Does the control pause all automatic motion or only one media element?
- Does it preserve position and let users resume from the same place?
- What alternatives exist for reduced motion, keyboard use, and touch?
- Find examples with no pause control and inspect whether the content changes on a timer.
