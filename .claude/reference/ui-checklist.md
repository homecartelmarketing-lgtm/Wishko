# UI Checklist — build and review

A fast pass over a screen before you call it done. It mirrors the `antislop-web` pre-flight
(Part C) with a few build-time reminders. Any unchecked box that is not deliberately waived is
a defect.

## Identity

- [ ] A `DESIGN.md` exists and this screen was generated against it.
- [ ] Exactly one signature element, present and nameable in one sentence.
- [ ] Everything re-tokenized to the client brand (no component-library default look).

## The AI tells (must all be absent)

- [ ] No `Inter` in a premium/creative context; a font with character is used.
- [ ] One accent only, saturation < 80%; no neon, no purple glow.
- [ ] No pure `#000`; off-black / zinc-950 instead.
- [ ] No three identical cards in a row; no centered hero when VARIANCE > 4.
- [ ] No emojis, no clipart, no custom cursors, no text gradient on big headers.
- [ ] No generic names ("John Doe", "Acme"); no fake round numbers (99.9%, 50%).
- [ ] No AI copy cliches ("Elevate", "Seamless", "Unleash", "Next-Gen").
- [ ] No broken image links; stable placeholders or SVG.

## Structure and states

- [ ] Loading (real-shape skeleton, not a spinner), empty (shows how to populate), error
      (clear inline) states all present.
- [ ] Inputs: label above, error below, focus ring in the accent.
- [ ] No overlapping/absolute-stacked elements fighting for the same zone.

## Layout and responsive

- [ ] CSS Grid, contained with a max-width and centered.
- [ ] `min-h-[100dvh]`, never `h-screen`.
- [ ] Collapses to one column below 768px; zero horizontal scroll at 320px.
- [ ] Tap targets >= 44px; body text >= 1rem; headlines use `clamp()`.

## Motion and performance

- [ ] Lightest animation tier that achieves the effect; no library duplicating a tier.
- [ ] Only `transform`/`opacity` animated; content visible by default.
- [ ] Everything under `prefers-reduced-motion: no-preference`.
- [ ] Animation effects have cleanup; perpetual ones isolated and memoized.
- [ ] `z-index` only for systemic contexts (nav, modal, overlay); no `z-50` spam.

## Accessibility

- [ ] Contrast AA on real backgrounds (text and interactive states).
- [ ] Visible focus on every interactive element.
- [ ] Semantic landmarks and heading order; images have alt text.
