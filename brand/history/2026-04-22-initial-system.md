# Session Notes: Initial Brand System (2026-04-22)

Log of the session that produced the initial Mythrun brand system.

## Scope

Started with nothing but a naming decision ("Mythrun") and ended with:
- Brand positioning brief (v0.4)
- Color palette (v1.0) with 60 tokens across 6 ramps
- Custom wordmark (Tyma Garamont with modified M swash)
- Pixel-art logomark at three logical resolutions (128, 64 canonical, 32 favicon)
- Two lockups (stacked primary, horizontal secondary)
- Five color variants of each component

## Workflow

Hybrid tool flow: Claude (conversational + Python scripting for pixel manipulation and SVG generation), Aseprite (pixel-level mark design), Illustrator (vector finalization + variant production + exports). This split worked well — Claude handled structural iteration and routine production, Aseprite handled pixel-level design work, Illustrator handled color variants and production exports.

Key technical notes:
- **PNG→JPEG upload bug**: Claude.ai's file upload pipeline converts PNG to JPEG, destroying alpha. Workaround: base64-encode the PNG and paste as standalone text message (not mixed with other text, which causes tokenization corruption).
- **Illustrator edge artifacts**: when importing SVG with many adjacent rects, Illustrator anti-aliases the internal edges between rects, producing visible grid lines. Fix: convert the SVG group to a compound path (Cmd+8) before export.
- **Aseprite Preview window does not downscale**: earlier guidance from Claude that you could preview at smaller sizes in Aseprite was wrong. The feature doesn't exist. Export to check smaller sizes, or use a second tool.

## Decision points

In rough chronological order:

1. **Brand positioning language.** Landed on "Parchment & Ink" archetype — literary-adjacent, Ghibli-contemplative, restrained. Rejected playful-fantasy and retro-game registers as too on-the-nose.
2. **Palette architecture.** Interactive OKLCH tuner used to pick anchor colors; collapsed to single neutral "paper" ramp plus one saturated accent (ember) plus four semantic colors (success/warning/danger/info).
3. **Wordmark typography.** Tyma Garamont Regular. Custom M swash with 3px rightward top-shift for optical compensation.
4. **Mark concept.** Started with a monogram, rejected. Converged on pixel-art quill after exploring what would read as both "writing/storytelling" and "computational/digital" without AI-branding cliché.
5. **Mark resolution.** Initial attempts at 48 too low-res (mushed the reference); pushed to 128 which preserved detail but was less emphatically pixel-art; settled on 64 as canonical after evaluating lockups. Full design rationale in `decisions.md`.
6. **Favicon (32).** Separately designed at 32 rather than downsampled. First attempt was too sparse; chunky-silhouette version was worse ("tick-like"); final version returned to sparse-stroke approach with tighter barb placement.
7. **Lockup layout.** Stacked chosen as primary over horizontal. The quill-into-M-h-gap alignment (observed during evaluation) elevated the stacked reading significantly.
8. **Lockup colors.** Monochrome ink-on-cream preferred over ember-mark + ink-wordmark. The dual-color version felt non-cohesive — like two separate things placed near each other rather than one lockup.

## Things produced

Files generated this session, organized by component:

**Documents:**
- Brand brief v0.4
- Palette specification v1.0 (markdown + HTML visual reference)

**Wordmark:**
- Four Illustrator masters (primary, reverse, black, white)
- SVG/PNG/PDF exports at production sizes from each master

**Logomark (64 canonical):**
- Source: pixel-art design in Aseprite, exported as PNG, converted to SVG via Python
- Five Illustrator masters (primary/ember, ink, reverse, black, white)
- Production exports from each

**Logomark (128 secondary):**
- Same file structure as 64, kept as higher-detail variant

**Favicon (32):**
- Designed in Aseprite, converted to SVG directly (no Illustrator step)
- Five SVG variants + five PNG variants produced programmatically

**Lockups:**
- Stacked: four Illustrator masters (four color variants × the stacked layout)
- Horizontal: four Illustrator masters (four color variants × the horizontal layout, mark-on-right)

## Things not yet done (for future sessions)

- Move all files into canonical repo structure under `brand/` (handled by first_steps_temp.md)
- Padded-canvas app-icon variants
- ICO favicon file
- Brand application examples (business card mockup, email signature, Discord server icon, social media headers) — would be useful but not urgent

## Self-assessment

What went well:
- Hybrid tool flow was efficient
- Iterative approach on mark design surfaced a compositional insight (quill-into-Mh-gap) that elevated the brand
- Sticking with monochrome lockup against initial instinct to introduce ember contrast
- Catching that 128 was too refined for the pixel-art register and pushing to 64

What could have gone better:
- Several rounds of miscommunication about PNG transparency (caused by the upload bug, not brand work)
- Claude gave bad advice on the 32 favicon (pushed toward chunky silhouette, which was rejected correctly by user)
- Claude's early suggestion that size-specific variants were unnecessary turned out to be wrong — the separately-designed 32 was genuinely needed

Lessons for future brand/design sessions:
- Trust the user's eye over generic design principles when they conflict
- Base64 workflow for pixel-accurate file transfer is reliable; use it by default for small pixel art
- Pixel art needs resolution matching between source and target (can't force-downsample detailed pixel illustrations to very small grids)
