# Mythrun Brand Guidelines v1.0

How to use the Mythrun brand. This is the day-to-day reference; `decisions.md` explains why these rules exist.

## Quick reference

| Element | Canonical | Location |
|---------|-----------|----------|
| Primary color (accent) | ember `#8A5A3C` | — |
| Text / ink | paper-900 `#231B12` | — |
| Background | paper-100 `#EFE9DC` | — |
| Wordmark typeface | Tyma Garamont Regular (wordmark-only, locked) | — |
| Body / prose typeface | Source Serif 4 (working pairing, may revisit) | Google Fonts, OFL |
| UI / data / mono typeface | IBM Plex Mono (working pairing, may revisit) | Google Fonts, OFL |
| Primary lockup | stacked, ink on cream | `brand/lockups/stacked/` |
| Secondary lockup | horizontal (mark-on-right), ink on cream | `brand/lockups/horizontal/` |
| Logomark (canonical) | 64-logical pixel art | `brand/logomark/64/` |
| Favicon | 32-logical, designed-at-size | `brand/logomark/favicon/` |
| Brand voice | Second-person, at-the-table (DM register) · Pope-pinned | `brand/brief.md` → Voice |
| Gradient technique | Dithered (4×4 Bayer, 8 px cell, 15% chaos, two-color) | Below → Texture |

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

The typography system below is a **solid first concept, not a final decision**. It's a working pairing that's good enough to ship with — we've evaluated candidates and this one made sense — but we may revisit it once the product is in real use and we have more signal. Committing now so design and development work isn't blocked on an open typography question.

**Wordmark typeface: Tyma Garamont Regular.** $49 commercial license, MyFonts. **Locked.** Used **only** for the "Mythrun" wordmark itself — not for headlines, marketing copy, body text, or UI chrome. In practice the wordmark is deployed from its exports (`brand/wordmark/exports/`) rather than typeset fresh, so Tyma Garamont is effectively a wordmark-only asset.

**Body / prose typeface: Source Serif 4.** Google Fonts, OFL license (no licensing friction for product or marketing). Use for long-form prose, marketing body copy, document text, and display headings until a dedicated display typeface is selected. Pairs with the Tyma wordmark by extending the literary / serif register; mood is calm, readable, warm-neutral.

**UI / data / monospace typeface: IBM Plex Mono.** Google Fonts, OFL license. Use for product UI chrome (buttons, labels, nav), data readouts (rolls, state, stats), code, and any place a "computational-but-crafted" register is wanted. Not a general body face — when prose gets long, switch back to Source Serif 4.

**Why this pairing.** Short version: serif body extends the literary register of the Tyma wordmark; monospace UI expresses the computational honesty of the product; the visual contrast between them mirrors Mythrun's internal separation between narrative layer (prose) and mechanical state layer (rolls, rules, system). Full rationale is in `decisions.md`.

**Fira Code was considered and rejected** as the UI monospace — it's a great coding typeface but too expressive for restrained product chrome. Fira Code remains the recommended personal dev-setup monospace for the team; it's just not the product's typeface.

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

## Texture · dithered gradients

Mythrun doesn't do smooth gradients. **Every gradient in the brand is rendered as a stepped Bayer dither between two colors.** Reference pin: *Return of the Obra Dinn*. Full rationale in `decisions.md` → "Why dithering is the gradient rendering technique."

### The dither formula (locked)

| Parameter | Value |
|-----------|-------|
| Threshold matrix | 4×4 Bayer |
| Cell size | 8 px at canonical scale (scale proportionally for different output sizes; grain stays visible) |
| Chaos blend | 15% pseudorandom, 85% ordered Bayer |
| Default axis | Vertical (ground above, accent below) |
| Horizontal axis | Allowed for section-break ribbons |
| Radial axis | Forbidden |
| Composition | Two-color, ground→accent. No three-stop gradients. |

### Color pairings

Ground is always `paper-100` (light) or `paper-900` (dark). Accent is a brand color.

- **Light → ember:** `paper-100` ground dithering to `ember-600`. The canonical warm gradient.
- **Light → ink:** `paper-100` ground dithering to `paper-900`. Quiet monochrome crossfade.
- **Dark → cream (reverse):** `paper-900` ground dithering to `paper-100`. Reverse / dark-mode gradient.

Combinations outside these pairings — e.g. `ember` ground or semantic colors (success / warning / danger / info) — are forbidden. The brand ground is always a paper step.

### Allowed uses

- Marketing hero backgrounds (wordmark or stacked lockup placed on the pure-ground portion of the panel, above the dither band).
- Section dividers in long-form documents (horizontal dither ribbons separating content blocks).
- Loading and transition screens in the product.
- Narrative-to-combat mode transitions in-product (conceptual — not yet spec'd).
- Data visualisation — dither-density as a quantitative axis in charts.
- Print accents: business cards, posters, merch.

### Forbidden uses

- **Smooth (CSS / SVG linear / radial) gradients anywhere in the brand.** If a crossfade is needed, it is dithered. There is no smooth-gradient fallback.
- Under body text. Reduces legibility.
- Behind or overlapping the wordmark, mark, or favicon — these stay on solid ground. The lockup sits above the dither band, not inside it.
- Radial gradients — even dithered. Radial reads as "glow," which is the opposite of the quiet frame.
- Three-stop (or more) gradients. Two colors only.
- `ember` as the ground color. Ground is always a paper step.
- In semantic color ramps (success / warning / danger / info). Dithering is brand expression, not a UI-state signal.
- Full-bleed across every touchpoint. Used sparingly — when a gradient moment is called for, not as a persistent texture.
- Inside the combat-mode rendering itself. Combat has its own aesthetic; dithered gradients belong to the brand frame.

## Voice

The brand's operational voice rules. Strategic context in `brief.md` → Voice.

**Default register:** second-person, present tense, at-the-table. Voice of a DM narrating a scene. The register is inherited directly from D&D's in-game narration ("you wake up in a tavern," "you roll initiative") — brand copy uses the same voice the product uses.

**Reference pin:** Lucas Pope (*Obra Dinn*, *Papers Please*). Terse, dry, craft-conscious, treats the product as a made object, a bit old-fashioned. Dry wit used sparingly.

**One voice, every subject.** Narrative and combat get the same register. Only the subject changes.

### Allowed moves

- Short sentences. One idea per sentence.
- Specific nouns over adjectives.
- Present tense by default.
- Assume TTRPG literacy — don't translate *initiative*, *party*, *roll*, *scene*, *DM*.
- Name the concrete — *the giant*, not "an encounter"; *the tavern*, not "a social space."
- Dry wit, sparingly. Wit earns its place by being true, not by being funny.

### Forbidden moves

- No hype register: "powered by AI," "revolutionary," "next-generation," "ultimate," "epic."
- No exclamation points, except inside in-game dialogue.
- No gamer-speak, natural-20 humor, or subreddit in-jokes.
- No first-person-plural "we" marketing. Team members speak in their own voices on social; the brand stays second-person.
- No softening combat into "tactical encounters" or "engagement modules." Combat is combat.
- No marketing the AI. The AI is infrastructure; the game is the product.
- No identity-presuming second-person ("as a busy professional…," "you're someone who…"). Second-person addresses the reader's *action* ("you roll," "you wake up"), not their demographic.

### Sub-modes

Default is *at-the-table*. Two situational shifts:

- **Session log** — retrospective, atmospheric. For taglines and evocative copy.
- **Maker's workshop** — explanatory, documentary. For feature pages, docs, and technical explanation.

### Copy ownership

Voice architecture is spec'd here. Actual brand copy — taglines, landing-page lines, product strings, marketing blurbs, error messages, onboarding — is the brand owner's to write. This spec does not include sample copy.

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
