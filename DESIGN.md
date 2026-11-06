# Design System: Wishko — Anti-Slop Minimalist Wishlist

## 0. Dials
VARIANCE: 6 | MOTION: 3 | DENSITY: 5

## 1. Atmosphere
Understated personal catalog. Quiet, editorial, and tactile. Feels like an architect's or designer's personal index of curated physical goods rather than a noisy affiliate marketing website. Generous white space, hairline borders, and zero neon ornamentation.

## 1b. Signature element (mandatory, exactly one)
**Editorial Index Ledger with Monospace Numbering & Clean Spec Rail** — Each item is presented with a sequential catalog index (`01`, `02`, `03`), clean micro-typography for specifications and category, and a tactile inline interaction for marking items as acquired.

## 2. Palette and Roles
- **Base Surface (Dark):** `#0c0d0e` — deep warm charcoal, not pure black
- **Card Surface (Dark):** `#141517` — quiet elevated plane
- **Border / Hairline (Dark):** `#222428` — subtle separation
- **Text Primary (Dark):** `#f4f4f6` — crisp readable ink
- **Text Secondary (Dark):** `#8b909a` — relaxed reading contrast
- **Text Muted (Dark):** `#535760` — metadata & indexing
- **Accent:** `#d9383a` — restrained vermilion (saturation < 75%), used strictly for focal links/states, never for neon glows or gradients
- **Light Theme Equivalents:** Chalk white (`#fafafa`), card (`#ffffff`), borders (`#e4e4e7`), text (`#18181b` / `#71717a`).

## 3. Typography
- **Display:** `Plus Jakarta Sans`, font-weight 600-700, tight tracking (`-0.03em`), proportional scale. No screaming uppercase H1s.
- **Body:** `Plus Jakarta Sans`, font-weight 400-500, relaxed leading, max line length 58ch.
- **Mono / Index:** `JetBrains Mono` / system monospace for indexing numbers (`01`, `02`), metadata pills, and status tags.
- **Banned:** `Inter` default font, screaming font weights, text gradients.

## 4. Components
- **Top Header Bar:** BANNED (removed per user instruction to eliminate generic app navbar). Controls (minimal theme toggle & share) placed unobtrusively in a quiet micro-utility header or footer.
- **Product Cards:** Clean framed image without floating emoji badges. Quiet border, zero heavy box-shadow drops.
- **Status Indicators:** Micro-dot or discreet monospace pill (`[ WANTED ]` / `[ ACQUIRED ]`), no emojis (no 🔥, 💊, ✨).
- **Buttons & Links:** Text link with directional arrow (`View on TikTok ↗`) and quiet ghost button for status toggle. No oversaturated pill buttons with glowing pink drop shadows.

## 5. Layout
- Grid with generous gutters (32px), asymmetric page rhythm, no cramped 3-box cookie-cutter feel.
- `max-w-6xl mx-auto px-6`.
- Mobile collapse: single column under 768px, zero horizontal overflow.

## 6. Motion
- Micro-interactions only: `transition: opacity 0.2s ease, transform 0.2s cubic-bezier(0.16, 1, 0.3, 1)`.
- Strictly wrapped with `prefers-reduced-motion` compliance.

## 7. Anti-patterns (BANNED)
- NO emojis anywhere in UI badges (🔥, 💊, ✨).
- NO neon pink / purple radial glows or background gradients.
- NO pure `#000000` pitch black.
- NO bulky generic SaaS navbar.
- NO three identical glossy cards.
- NO fake stats counters or generic marketing badges ("Curated Collection").
