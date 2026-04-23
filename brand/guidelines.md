# Mythrun Brand Guidelines v1.0

How to use the Mythrun brand. This is the day-to-day reference; `decisions.md` explains why these rules exist.

## Quick reference

| Element | Canonical | Location |
|---------|-----------|----------|
| Primary color (accent) | ember `#8A5A3C` | — |
| Text / ink | paper-900 `#231B12` | — |
| Background | paper-100 `#EFE9DC` | — |
| Wordmark typeface | Tyma Garamont Regular (wordmark-only) | — |
| Display / body typefaces | Not yet selected | — |
| Primary lockup | stacked, ink on cream | `brand/lockups/stacked/` |
| Secondary lockup | horizontal (mark-on-right), ink on cream | `brand/lockups/horizontal/` |
| Logomark (canonical) | 64-logical pixel art | `brand/logomark/64/` |
| Favicon | 32-logical, designed-at-size | `brand/logomark/favicon/` |

## Color palette

Six ramps × ten steps each = 60 tokens. See `brand/palette/palette.md` for the full token list with OKLCH values and semantic assignments.

**Core anchors:**
- `ember-600` = `#8A5A3C` — the only saturated color in regular use
- `paper-100` = `#EFE9DC` — default background
- `paper-900` = `#231B12` — default text / ink color
- `paper-700` = `#3D3528` — secondary ink (body copy in hierarchy)
- `paper-500` = `#877F72` — tertiary ink (captions, metadata)

**Semantic colors (use sparingly, only for status UI):**
- `success-500` = `#6D7A3E`
- `warning-500` = `#B07835`
- `danger-500` = `#B55A48`
- `info-600` = `#4A6B82`

**Usage rules:**
- Default every composition to paper-900 on paper-100. This is the canonical brand color combination.
- Use ember only as a deliberate accent, not as a default. A full page with ember elements everywhere dilutes it.
- Semantic colors are for UI state only (error messages, success notifications, etc.), not for brand expression.
- When reversing (dark mode), use paper-100 text on paper-900 background. Do not use white text on pure black unless required.

## Typography

**Wordmark typeface (Tyma Garamont Regular).** $49 commercial license, MyFonts. Used **only** for the "Mythrun" wordmark itself — not as a display typeface, body typeface, or general brand face. Marketing headlines, product UI, and body copy do not use Tyma Garamont. In practice the wordmark is deployed from its exports (`brand/wordmark/exports/`) rather than typeset fresh, so Tyma Garamont is effectively a wordmark-only asset.

**Display typeface:** not yet selected. No typeface has been committed for headlines, marketing, or product UI beyond the wordmark itself. TBD in a future decision.

**Body typeface:** not yet selected. When picking body type, choose something that sits comfortably next to the Tyma wordmark in a lockup — a readable serif or a slightly humanist sans. Avoid geometric sans (Futura, Gotham-family) which clashes with Tyma's warmth. Candidates worth exploring: Söhne, Inter, system-ui stack.

**Wordmark-specific specs:**
- Cap-height = 73.2% of total wordmark height (Y descender extends below baseline)
- Clear-space rule: cap-height of empty space on all four sides
- M swash has a 3px rightward apex top-shift (optical compensation). This is intentional; do not "correct" it.

## The mark

Two logical resolutions are in the production system. Each has a specific use.

**64 (canonical).** The default mark. Use everywhere the mark appears in composition with other elements (lockups, header layouts, marketing materials) and everywhere the mark appears at large display sizes (48px and up). Scale with nearest-neighbor only; smooth scaling destroys the pixel character.

**32 (favicon).** Use only at 32×32 display and smaller. Browser favicons, bookmarks bar, small search result icons. Never upscale the 32 — it's not designed to hold up at larger sizes.

**Mark color variants:**
- `primary` — ember `#8A5A3C` — use when the mark appears alone or on cream backgrounds without a wordmark
- `ink` — paper-900 `#231B12` — use in lockups (mark and wordmark same color)
- `reverse` — paper-100 `#EFE9DC` — use on charcoal/dark backgrounds
- `black` — pure `#000000` — use for legal documents, one-color print, or contexts requiring true black
- `white` — pure `#FFFFFF` — use on merch or contexts requiring true white

**Clear space for the mark alone:** 0.3 × mark height on all four sides.

**Minimum size:** the 64 canonical displays down to about 48×48 before losing legibility. Below 48px, switch to the 32 favicon variant.

## The lockups

### Primary lockup (stacked)

Mark above wordmark, both in paper-900 (ink on cream). Used for the vast majority of brand applications: site headers, marketing materials, document signatures, business cards.

**Proportions (locked):**
- Bounding box aspect ratio: 1.52 : 1 (slightly wider than tall)
- Mark height = 2.0 × wordmark cap-height
- Vertical gap (mark bottom to wordmark top) = 0.55 × wordmark cap-height
- Mark centered horizontally on wordmark midpoint

**Clear space:** 1 × cap-height on all four sides of the bounding box.

**Why the composition works:** the quill tip aligns with the gap between M and h, reading as the quill actively dipping into the word. Do not adjust mark position vertically — this alignment is the reason the composition is strong.

### Secondary lockup (horizontal, mark-on-right)

Wordmark on the left, mark on the right. Used when horizontal space is abundant but vertical space is limited — site nav bars, email signatures, narrow headers.

**Proportions (locked):**
- Bounding box aspect ratio: 3.85 : 1 (wide)
- Mark height ≈ 1.78 × wordmark cap-height
- Horizontal gap (wordmark right edge to mark left edge) = 80px at canonical size (adjust proportionally when scaling)
- Mark centered vertically on wordmark midpoint

**Clear space:** 1 × cap-height on all four sides of the bounding box.

**Why mark-on-right:** the M swash and quill's upper-right lean create a bookend composition — the wordmark is framed by two outward-reaching gestures. Mark-on-left produces visual conflict between the swash and quill.

### Lockup color variants

Each lockup exists in four color variants:

- `primary` — paper-900 on transparent (for cream contexts)
- `reverse` — paper-100 on transparent (for charcoal contexts)
- `black` — pure black on transparent (for legal / one-color contexts)
- `white` — pure white on transparent (for merch contexts)

Note: lockup `primary` is monochrome (both elements in paper-900), not dual-color with ember mark + ink wordmark. The monochrome version reads as a unified composition; the dual-color version was tested and rejected as feeling non-cohesive.

## Don'ts

**Never:**
- Recolor the mark outside the canonical palette. No custom colors, no gradients, no effects.
- Apply effects to the mark: no drop shadows, glows, strokes, or embosses.
- Scale the 32 favicon above 32×32.
- Downsample the 64 with smooth/bicubic filtering. Always nearest-neighbor.
- Flip the mark horizontally or vertically. The canonical orientation is fixed.
- Rotate the mark.
- Use ember as a default background color. Ember is an accent, not a ground.
- Combine the ember mark with an ink wordmark in a lockup. Lockups are monochrome.
- Use dual-color ember/ink compositions outside of carefully-considered marketing materials.
- Stretch or skew any brand element. Proportions are locked.
- Recreate the mark at non-canonical resolutions (e.g., 128, 96, 48). Use 64 for anything 48+ and 32 for anything under 48.
- Use a typeface other than Tyma Garamont Regular for the wordmark.

**Avoid:**
- Placing the mark against visually busy backgrounds. If a background has patterns or photography, add a cream or charcoal plate behind the mark.
- Using the mark smaller than 48×48 (switch to favicon variant).
- Placing text in ember. Ember is a mark/accent color; text in ember becomes illegible against cream backgrounds and off-tone against charcoal.
- Over-using the mark. One instance per composition is usually enough.

## File naming

All canonical files follow this pattern:

```
mythrun-[component]-[variant].[ext]

component: wordmark, mark, lockup-stacked, lockup-horizontal, favicon-32
variant:   primary, reverse, ink, black, white
ext:       ai (source), svg (vector export), png (raster export), pdf (print)
```

PNG exports include a size suffix: `mythrun-wordmark-primary-512.png`, `mythrun-wordmark-primary-1024.png`, etc.

## When in doubt

Default to monochrome (paper-900 on paper-100). Default to the stacked lockup. Default to the 64 mark. Default to generous clear space. Default to quiet.

The brand's register is restraint. When a decision feels too loud, too colorful, too dynamic — it probably is. Make it quieter and try again.
