# mythrun-design

Brand assets for Mythrun — AI-powered multiplayer D&D 5e platform.

## Invariants

- **Primary color:** ember `#8A5A3C`
- **Text/ink color:** paper-900 `#231B12`
- **Background color:** paper-100 `#EFE9DC`
- **Wordmark typeface:** Tyma Garamont Regular (locked, wordmark-only)
- **Body / prose typeface:** Source Serif 4 (Google Fonts, OFL) — working pairing, subject to future revision
- **UI / data / monospace typeface:** IBM Plex Mono (Google Fonts, OFL) — working pairing, subject to future revision
- **Primary lockup:** stacked (mark above wordmark), both in paper-900 on cream
- **Canonical mark resolution:** 64 logical pixels (not 128)

Never change these without updating both this file and `brand/decisions.md`.

## Map

| Question | File |
|----------|------|
| What's the brand positioning? | `brand/brief.md` |
| How do I use the marks / lockups / colors? | `brand/guidelines.md` |
| Why is it the way it is? | `brand/decisions.md` |
| What's the palette in detail? | `brand/palette/palette.md` |
| What happened in a past session? | `brand/history/` |

## Working conventions

- Source files (`.ai`) go in `source/` subdirectories
- Production exports (`.svg`, `.png`, `.pdf`) go in `exports/` subdirectories
- File naming: `mythrun-[component]-[variant].[ext]` (e.g. `mythrun-wordmark-primary.svg`)
- Color variant names: `primary`, `reverse`, `ink`, `black`, `white`
- Never ship exports without a corresponding `.ai` source file checked in

## Status

- Brief: locked (v0.4)
- Palette: locked (v1.0)
- Wordmark: locked, exports done
- Logomark: locked (64 canonical), exports done
- Favicon (32): locked, exports done
- Lockups: locked, exports done
- Guidelines doc: done (v1.0)
- Folder structure: done (v1.0)
