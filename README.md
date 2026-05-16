# Landing Page UI Kit

The actual deliverable: a single-page personal landing for **nixiecon**.

## What's here

- `index.html` — the complete page. All CSS inline. No JS. Google Fonts only (external).

## Structure

```
status pill         (top, "online · sometimes")
wordmark            (Instrument Serif italic, ~144px, glow + blinking cursor)
tagline             (Space Grotesk light, 2 lines, one in serif italic)
link buttons        (mono, lowercase, with ↗ arrow on each)
footer              (mono metadata, bottom)
corner ticks        (4 corners, frame the void)
```

## Key effects

- **The bloom** — a single radial gradient (`#8b5cf6`, 720px, blurred 60px) behind the wordmark. The only light source on the page. It breathes at 4s.
- **Dot grid** — 1px violet dots at 24px pitch, masked by a center-out radial fade so it vignettes.
- **Cursor blink** — a `_` after the wordmark, blinks 1.1s, terminal-style.
- **Hover glow** — link buttons gain a violet glow on hover; the `↗` arrow nudges 2px diagonally.
- **Status dot** — pulses 2s, drives home "online · sometimes".
- **Corner ticks** — four L-shaped 16px hairlines in each corner. A visual frame for the void.

## Content slots

Edit these directly in `index.html`:

| Slot | Default | Where |
|---|---|---|
| Status text | `online · sometimes` | `.status` |
| Wordmark | `nixiecon` | `h1.wordmark` |
| Tagline | `builds small tools after midnight.` + `writes code that glows in the dark.` | `p.tagline` |
| Links | GitHub, LinkedIn, X, Email | `nav.links` |
| Footer | `// nixiecon · est. 2026 · made in the dark` | `footer` |

## Single-file rule

The brief required **one** `index.html` with inline CSS, no external deps and no JS. This file is the canonical deliverable — copy it standalone and it works. The rest of this design system supports it (rationale, tokens, alternates) but is not required to ship.

## Responsive

Below 520px: padding tightens, bloom shrinks, link labels collapse (only icons + arrow stay), footer compresses. The page is single-column always — no breakpoints for layout, just for density.

## Accessibility

- `prefers-reduced-motion` disables the bloom breathing, cursor blink, and status pulse.
- All links have `aria-label` for icon-only mobile state.
- Contrast: foreground `#ede9fe` on `#0a0614` is ~17:1.
