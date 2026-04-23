# Mythrun Palette v1.0

Parchment & Ink archetype. Near-monochrome with a single saturated accent (ember) and four semantic colors for UI state.

## Architecture

- **6 ramps** × **10 steps each** = **60 color tokens**
- Generated via OKLCH interpolation from a small set of anchor colors
- All ramps strictly monotonic in perceptual lightness
- WCAG AA compliance: paper-900/paper-100 combinations meet 4.5:1 contrast threshold for body text at normal sizes

## Anchors

User-selected via interactive tuner during design phase:

| Token | Hex | Role |
|-------|-----|------|
| `ember-600` | `#8A5A3C` | Primary accent, the mark color |
| `paper-100` | `#EFE9DC` | Default background |
| `paper-700` | `#3D3528` | Secondary ink |
| `paper-900` | `#231B12` | Primary text / ink |
| `success-500` | `#6D7A3E` | UI state: success |
| `warning-500` | `#B07835` | UI state: warning |
| `danger-500` | `#B55A48` | UI state: danger |
| `info-600` | `#4A6B82` | UI state: info |

## The six ramps

Each ramp goes from 50 (near-white, if applicable) through 900 (near-black). Here's the abbreviated anchor-step set; the full 10-step OKLCH-interpolated ramp is in the CSS/Tailwind exports and in `palette.html`.

### paper (neutral, 10 steps)

Collapsed from three separate neutral anchors. Spans from near-white through the cream ground and into deep ink.

Key steps:
- `paper-50` — near-white, reserved (rarely used)
- `paper-100` — `#EFE9DC` — default background
- `paper-300` — mid-light neutral, borders / dividers
- `paper-500` — mid neutral, captions / metadata
- `paper-700` — `#3D3528` — secondary ink (body copy in hierarchy)
- `paper-900` — `#231B12` — primary text / ink

### ember (warm saturated accent, 10 steps)

The only saturated ramp in regular use. Anchor at step 600.

Key steps:
- `ember-300` — light ember tint (backgrounds, subtle highlights)
- `ember-600` — `#8A5A3C` — the mark color, the default accent
- `ember-800` — deep ember (hover states, pressed UI)

### success (muted green, 10 steps)

Anchor at step 500 (`#6D7A3E`). Muted, not electric — fits the Parchment & Ink register. Used for UI success states only.

### warning (amber, 10 steps)

Anchor at step 500 (`#B07835`). Warm but desaturated. UI warning states.

### danger (muted red, 10 steps)

Anchor at step 500 (`#B55A48`). Warm red that matches ember temperature, not a bright corporate red. UI error states.

### info (muted blue, 10 steps)

Anchor at step 600 (`#4A6B82`). Cool but restrained. UI informational states.

## Usage rules

**Brand expression colors** (for marketing, marks, headlines):
- Default: paper-900 ink on paper-100 cream
- Accent: ember-600, used sparingly
- Never: semantic colors (success/warning/danger/info) — these are for UI state only

**UI colors** (for product interfaces):
- Text: paper-900 (primary), paper-700 (secondary), paper-500 (tertiary)
- Backgrounds: paper-100 (default), paper-50 (elevated surfaces), paper-200 (subdued backgrounds)
- Borders / dividers: paper-300
- Interactive accents: ember-600 (links, primary buttons)
- Status: success/warning/danger/info at 500-600 steps

**Accessibility:**
- Body text: paper-900 on paper-100 = 13.5:1 contrast (exceeds AA and AAA)
- Secondary text: paper-700 on paper-100 = 8.2:1 (exceeds AA and AAA)
- Tertiary text: paper-500 on paper-100 = 4.7:1 (meets AA for normal text)
- Avoid: ember on paper-100 for body text (marginal contrast; fine for accents and small UI elements but not for long-form reading)

## Exports

- CSS custom properties: all 60 tokens as `--paper-100`, `--ember-600`, etc.
- Tailwind config: drops in as a `colors` extension
- Figma-importable JSON: for eventual design system work
- Visual reference: `palette.html` in this directory
