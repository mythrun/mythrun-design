# Brand Design Decisions

Context for why the Mythrun brand is the way it is. Load this when you need to understand the reasoning behind a decision — don't load it for every task.

## The quill as logomark

The mark is a pixel-art quill in ember color. This works on multiple semantic layers simultaneously:

**Writing / storytelling layer.** A quill is the single most concentrated signifier of "this is about shared narrative" — it invokes scribes, novelists, playwrights, and game masters in one image. For a tabletop-RPG-adjacent product, this carries the brand's core claim (Mythrun is a platform for collaborative storytelling) without having to say it.

**Digital / AI layer.** The pixelation renders the quill as a computational artifact. But crucially, it uses a *specific* computational aesthetic — not the current AI-branding visual language (glowing gradients, sparkles, ethereal forms), which has become shorthand for "AI slop" among craft-conscious audiences. Pixel art instead signals "deliberate, constrained, hand-considered, computational-but-crafted." It reaches back to an earlier era of computing when programmers were craftspeople, and is visually owned by indie developers and pixel art communities — exactly the crowd whose respect the brand needs.

**The combination is greater than the sum.** A quill alone would be derivative. Pixel art alone would read as generic indie-game aesthetic. Quill-in-pixel-art occupies a specific semantic space: an AI dungeon master rendered as a considered digital artifact that honors both storytelling tradition and computational craft. This is the space Mythrun actually occupies.

Future brand decisions should reinforce this register: craft-conscious, specifically-computational, respectful-of-narrative-tradition.

## Why 64 logical pixels (not 128)

A 128-logical mark looks refined at any display size but reads less confidently as pixel art. A 64-logical mark at the same display size has pixels that are 2× chunkier, so the pixel-art register declares itself more clearly. In lockup with the wordmark, the 64 felt more "Mythrun" than the 128 — the chunky-pixel register matched the brand voice better than the fine-pixel version.

128 was explored during ideation but is not part of the production system; the 128 pixel art is archived in `brand/history/ideation/` as a brainstorming artifact, not a usable variant. 32 is a separately-designed favicon variant, not a downsample.

## Why Parchment & Ink palette

The brief positions Mythrun as literary-adjacent, patient, Ghibli-contemplative. Saturated colors would fight that voice. The palette is near-monochrome — ember (the only saturated color) appears sparingly as an accent, and all other work is done with paper tones. This gives the brand a restraint that reads as considered rather than playful.

The ember is specifically a muted, warm, lantern-light shade (#8A5A3C), not a bright or corporate orange. It reads as old paper under firelight — the right mood for the tabletop-fantasy register without being literally fantasy-coded.

## Why the stacked lockup is primary

Two reasons emerged from testing:

**The quill-tip-into-Mh-gap alignment.** In the stacked composition with the 64 mark, the quill's lean-up-right positions the tip pointing into the gap between the M and the h in "Mythrun." This reads as the quill actively dipping into the word — semantic continuity between mark and wordmark. The mark isn't decoration; it's depicting the act of writing Mythrun. "Feather in the cap" is a secondary reading that reinforces the "accomplishment / adventure" theme.

**The horizontal has M-swash tension.** The M swash leans up-and-left; the quill's lean is up-and-right. In horizontal-with-mark-on-left, these gestures compete for the same visual space above the wordmark. The mark-on-right-with-original-orientation composition resolves this (swash and quill become bookends, framing the word) and serves as the secondary lockup.

Both lockups are canonical. Stacked is primary; horizontal-mark-on-right is secondary.

## Why the mark isn't flipped

Flipping the quill would improve the horizontal-mark-on-left composition but break the stacked composition's tip-into-Mh-gap alignment. Since stacked is primary, the quill orientation is locked as the original (leaning up-right).

## Why a separate 32-favicon variant

The 128 and 64 marks rely on visible pixel structure (barbs, shaft, nib) for character. Downsampled to 32, those details blur into unreadable noise — the mark becomes a brown smudge. The 32 variant is designed-at-32, with deliberately sparse pixel placement that reads clearly at favicon size. It does not upscale well and should never be used above 32×32 display.

## Why the wordmark uses Tyma Garamont

Considered against other Garamond revivals and general serif options. Tyma Garamont has a specific quality — warm, slightly irregular, handmade-feeling — that matches the Parchment & Ink register better than more refined digital Garamond revivals. The custom M swash extends this handmade quality into something specific to Mythrun. The 3px rightward top-shift of the M apex is an optical compensation that keeps the letterform feeling intentional at display sizes.

## Things that were considered and rejected

- **Radial-symmetric mark** (circle/hexagon with internal feather): rejected for reading too much like current AI branding. Abandoned early in logomark exploration.
- **Monogram (M-based mark)**: explored but felt insufficient — wasn't doing enough semantic work for the brand.
- **Chunky silhouette 32 favicon**: attempted as "strip to silhouette at small sizes" per conventional wisdom, rejected because the silhouette without internal pixel detail looked generic ("tick-like"). The sparse-stroke approach preserves what makes the mark Mythrun's even at small size.
- **Flipped quill**: considered for horizontal-lockup cleanliness but rejected because flipping propagates everywhere (once flipped, always flipped), and breaks the stacked composition's semantic alignment.
- **Horizontal lockup as primary**: rejected in favor of stacked. The stacked composition's quill-into-word semantic reading was too valuable to demote.

## Open questions / future work

- Padded-canvas variant of the mark (mark in larger canvas with safe-area padding, for iOS/Android app icon contexts that expect padding): not yet produced, produce if/when app icon submission requires it.
- ICO favicon file (vs just PNG favicon): not yet produced, produce when setting up website favicon.
- Alternate horizontal lockup with mark flipped (and its implications): tabled, do not pursue without revisiting the canonical-orientation decision.
