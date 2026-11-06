# Design Vocabulary — the Tailwind "how" behind the anti-slop rules

Concrete class recipes that implement `antislop-web`. The skill says WHAT to do; this file
shows one clean way to do it in Tailwind. Adapt to your token system; do not copy blindly.

## Type scale (hierarchy by weight and color, not giant size)

```
Display   text-4xl md:text-6xl font-semibold tracking-tighter leading-none
H2        text-2xl md:text-3xl font-semibold tracking-tight
H3        text-lg font-medium
Body      text-base leading-relaxed max-w-[65ch] text-zinc-600 dark:text-zinc-400
Small     text-sm leading-relaxed
Mono/num  font-mono tabular-nums tracking-tight
```

- Fluid headline: `text-[clamp(2rem,6vw,4rem)]`.
- Never scale hierarchy by size alone; pair size with weight and color.

## Spacing and rhythm

- Section vertical rhythm: `py-[clamp(3rem,8vw,6rem)]`.
- Container: `max-w-7xl mx-auto px-4 md:px-6` (or `max-w-[1400px]`).
- Stack gaps with `space-y-*` / `gap-*`, never manual margins between siblings.
- Full height: `min-h-[100dvh]` — never `h-screen`.

## Color tokens (one accent, neutral bases, no #000)

```
Base bg      bg-zinc-50 dark:bg-zinc-950        (off-black, never #000)
Surface      bg-white dark:bg-zinc-900
Border       border-zinc-200 dark:border-zinc-800
Text         text-zinc-900 dark:text-zinc-100
Muted        text-zinc-500
Accent       (one only, sat < 80%) e.g. emerald-600 / sky-600 / rose-600
```

- Accent used for one job (primary action, focus ring, one highlight). Do not spray it.
- Tinted shadow toward the background: `shadow-[0_8px_30px_rgb(0,0,0,0.06)]`.

## Component states (materiality)

```
Button    px-4 py-2 rounded-lg font-medium transition
          active:translate-y-[1px] active:scale-[0.99]
          focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-[accent]
          (no outer glow, no custom cursor)
Input     flex flex-col gap-2
          <label class="text-sm font-medium">
          <input class="rounded-lg border px-3 py-2 focus-visible:ring-2 ring-[accent]">
          <p class="text-sm text-red-600"> (error BELOW)
Card      only when elevation communicates hierarchy; in high density use border-t / divide-y
```

## Layout patterns (break the generic default)

- Asymmetric hero: `grid md:grid-cols-[1.2fr_0.8fr]` with an image fade on one side.
- Instead of three identical cards: 2-column zig-zag (`md:grid-cols-2` with alternating
  `md:[&:nth-child(even)]:mt-16`), an asymmetric bento, or horizontal scroll.
- Always CSS Grid over flex-math; never `w-[calc(33%-1rem)]`.
- Divider-driven density: `divide-y divide-zinc-200` instead of card boxes.

## Motion (lightest tier, transform/opacity only)

- CSS-only reveal (0 JS):
  ```
  @media (prefers-reduced-motion: no-preference) {
    .reveal { animation: reveal linear both; animation-timeline: view(); }
  }
  @keyframes reveal { from { opacity:0; transform:translateY(1rem);} to {opacity:1;transform:none;} }
  ```
- Content visible by default; the animation only enhances.
- Stagger a list; do not mount it all at once.
- Only `transform` and `opacity`. Grain/noise in a `fixed inset-0 pointer-events-none` layer.

## Responsive (non-negotiable)

- Everything multi-column collapses to one column below 768px.
- Zero horizontal scroll (critical failure). Test at 320px.
- Tap targets min 44px; body min `1rem`.
