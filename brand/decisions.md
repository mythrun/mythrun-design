# Brand Design Decisions

Context for why the Mythrun brand is the way it is. Load this when you need to understand the reasoning behind a decision — don't load it for every task.

## The quill as logomark

The mark is a pixel-art quill in ember color. This works on multiple semantic layers simultaneously:

**Writing / storytelling layer.** A quill is the single most concentrated signifier of "this is about shared narrative" — it invokes scribes, novelists, playwrights, and game masters in one image. For a tabletop-RPG-adjacent product, this carries the brand's core claim (Mythrun is a platform for collaborative storytelling) without having to say it.

**Digital / AI layer.** The pixelation renders the quill as a computational artifact. But crucially, it uses a *specific* computational aesthetic — not the current AI-branding visual language (glowing gradients, sparkles, ethereal forms), which has become shorthand for "AI slop" among craft-conscious audiences. Pixel art instead signals "deliberate, constrained, hand-considered, computational-but-crafted." It reaches back to an earlier era of computing when programmers were craftspeople, and is visually owned by indie developers and pixel art communities — exactly the crowd whose respect the brand needs.

**The combination is greater than the sum.** A quill alone would be derivative. Pixel art alone would read as generic indie-game aesthetic. Quill-in-pixel-art occupies a specific semantic space: an AI dungeon master rendered as a considered digital artifact that honors both storytelling tradition and computational craft. This is the space Mythrun actually occupies.

Future brand decisions should reinforce this register: craft-conscious, specifically-computational, respectful-of-narrative-tradition.

## Why the brand has two modes: frame and content

A Mythrun session is two games stitched together: **narrative mode** (roleplay, dialogue, description, decisions) and **combat mode** (tactical, voxel-rendered, spatial, turn-based). Early brand work over-rotated toward the narrative half — "literary, not gamey" language read as if Mythrun were a writing tool rather than a game. That was wrong. Mythrun is a game. The game has two halves. The brand has to acknowledge both.

The architecture the brand actually wants: the brand is the **frame**, not the content. The frame stays quiet, muted, Parchment & Ink — all the marks, lockups, colors, and typography already specified. Inside the frame, narrative and combat content both live. Narrative content reads as an extension of the frame's quiet register. Combat content is rendered in voxel space, is deliberately more colorful and contrast-y than the frame, and fills most of the screen when active. The frame does not pretend combat doesn't exist; combat does not colonize the frame.

The combat palette is **out of brand scope**. It lives inside the frame but isn't part of the brand color spec. The brand palette constrains itself (ember + paper + four semantic tokens); the combat palette is intentionally more diverse — muted-but-contrasty, retro-voxel-coded, bright without being childish. When combat-palette decisions need to be made, they happen in a separate spec downstream of this one.

## Why dithering is the gradient rendering technique

The logomark is pixel art. The combat mode is voxel-rendered. Both sit in the same craft-computational aesthetic lineage — which the brand frame otherwise underrepresents. To acknowledge the game register in the frame without adopting the combat palette, **dithering replaces smooth interpolation anywhere a gradient would otherwise appear.** Smooth CSS / SVG gradients are forbidden anywhere in the brand. If a crossfade between two colors is needed, it is rendered as a stepped Bayer dither.

This is a stronger claim than "dithering is a texture device." It means the technique is locked into every gradient moment the brand produces — footer transitions, splash / loading screens, narrative → combat transitions in-product, error and 404 screens, social / OG share images, and print accents. The gradient *is* the dither.

The rule has a practical consequence: the brand only uses the technique where genuine color contrast is committed to. Website section dividers look appealing in brand-guideline isolation but fail in real page layouts where most section transitions are cream-on-cream and have no contrast to dither between. The rule isn't "dither every section break"; it's "wherever the brand commits to a high-contrast color transition, that transition is dithered."

Reference pin: Lucas Pope's **Return of the Obra Dinn**. 1-bit ordered dithering replaces smooth shading throughout the game; the distinctive look comes from the technique being applied everywhere, not from sprinkling it in. Mythrun does the same: whenever a gradient is rendered, it is rendered dithered.

**Parameters (the brand's dither formula):**

- **4×4 Bayer threshold matrix** — small enough to stay chunky and readable, coarser than 8×8, preserves the pixel-art register.
- **8 px cell size at canonical scale** — each Bayer cell is one 8-pixel square. Scales proportionally for different output sizes; the grain should stay visible as grain.
- **15% chaos** — blend of ordered Bayer (crisp) and pseudorandom noise (grain). 0% reads mechanical; 100% reads like noise; 15% is the sweet spot — breaks the perfect-grid feel without losing legibility.
- **Vertical axis default, horizontal allowed, no radial** — vertical matches a horizon (ground above, terrain/light below). Horizontal is reserved for section-break ribbons. Radial is forbidden because it pulls toward "glow," which is the opposite of the quiet frame.
- **Two-color ground→accent composition** — ground is always `paper-100` (light) or `paper-900` (dark); accent is a brand color (ember or the opposite paper step). No three-stop gradients.

Dithering still applies *sparingly* in the sense that the brand doesn't dither every surface — most of the frame stays on solid ground. But when a gradient moment does happen, it is always dithered. There is no smooth-gradient fallback. See `guidelines.md` for the operational rules.

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

## Why Source Serif 4 + IBM Plex Mono (working pairing)

Framed explicitly as a **solid first concept**, not a final decision. The pairing was committed to so design and development work isn't blocked on an open typography question, and it may be revisited once the product is in real use and we have more signal.

**Body / prose: Source Serif 4 (Google Fonts, OFL).** A serif body extends the literary register of the Tyma wordmark. Mythrun's lineage is literary-adjacent (Le Guin, Tolkien, Wolfe), and a serif body stays in that register without quoting the wordmark. Source Serif 4 is warm, readable at text sizes, and contemporary without being self-consciously "design-y." OFL licensing removes friction for product and marketing use.

**UI / data / monospace: IBM Plex Mono (Google Fonts, OFL).** Monospace in the UI expresses the computational honesty of the product. Mythrun runs on structured state — character sheets, rolls, scene graphs, logs — and a monospace UI chrome makes that machinery legible rather than hiding it behind polished product-marketing typography. IBM Plex Mono is restrained, even-toned, reads neutrally at small sizes, and doesn't shout.

**The pairing mirrors the product's internal structure.** Serif body = narrative layer (prose, fiction, the stuff the players experience). Monospace chrome = mechanical layer (state, rules, the stuff the system tracks). The visual contrast between the two mirrors the separation Mythrun holds between those two layers — not a stylistic quirk, but a direct expression of how the product is organized.

**Fira Code was considered and rejected** for UI monospace. It's a great coding typeface, but the ligatures and slight expressiveness are too much for restrained product chrome — UI labels and data blocks don't want arrows and triple-equals ligatures. Fira Code remains the recommended personal dev-setup monospace for the team; it's just not the product's typeface.

**Not yet decided:** a dedicated display typeface for large marketing headlines. Source Serif 4 at larger sizes is fine for now. If headline density becomes a problem later (Source Serif 4 can feel soft at marketing display sizes), revisit with a more characterful display serif or a condensed companion.

## Why the brand voice is second-person at-the-table

D&D's in-game narration voice is already second-person — "you wake up in a tavern," "you roll initiative," "you turn and see the dragon." When Mythrun the product speaks to the player mid-session, that's the register it uses. When Mythrun the brand speaks to a stranger in marketing copy, it keeps that same register. The brand voice inherits the DM's voice directly; brand copy and product copy share the same tonal world, intentionally.

Reference pin for the voice: **Lucas Pope** (*Obra Dinn*, *Papers Please*). Terse, dry, craft-conscious, treats the product as a made object, a bit old-fashioned. Dry wit used sparingly — never to soften or hype.

**One voice covers every subject.** The same voice describes a quiet narrative moment and a tactical combat turn. Only the subject changes; the register does not. Granting combat its own voice would undo the frame-vs-content architecture — the frame is supposed to hold both halves without shifting register itself.

The audience is the TTRPG craft crowd — players who already get what "craft-conscious game" means. The brand voice doesn't sell the category, doesn't translate shared vocabulary (*initiative*, *party*, *roll*, *DM*), and doesn't explain the obvious.

Second-person that addresses the reader's **action** ("you roll," "you wake up") is DM register and allowed. Second-person that **presumes the reader's identity** ("as a busy professional…," "you're someone who…") is marketing register and forbidden — Mythrun does not speak in marketing register about its reader. Full operational rules in `guidelines.md`.

## Things that were considered and rejected

- **Radial-symmetric mark** (circle/hexagon with internal feather): rejected for reading too much like current AI branding. Abandoned early in logomark exploration.
- **Monogram (M-based mark)**: explored but felt insufficient — wasn't doing enough semantic work for the brand.
- **Chunky silhouette 32 favicon**: attempted as "strip to silhouette at small sizes" per conventional wisdom, rejected because the silhouette without internal pixel detail looked generic ("tick-like"). The sparse-stroke approach preserves what makes the mark Mythrun's even at small size.
- **Flipped quill**: considered for horizontal-lockup cleanliness but rejected because flipping propagates everywhere (once flipped, always flipped), and breaks the stacked composition's semantic alignment.
- **Horizontal lockup as primary**: rejected in favor of stacked. The stacked composition's quill-into-word semantic reading was too valuable to demote.
- **Fira Code as the UI monospace**: rejected because its ligatures and expressiveness are too much for restrained product chrome. Remains the recommended personal dev-setup monospace for the team; just not the product's typeface. See the typography decision for full reasoning.
- **A separate "combat voice" as a second brand register**: rejected in favor of one-voice-every-subject. Two voices would undo the frame-vs-content architecture and double the writing work without earning its keep.
- **Invented voice samples in the brief**: the earlier "Voice samples" block in `brief.md` was not user-authored and was removed. Voice is now spec'd as principles and rules; brand copy itself is the brand owner's to write.

## Open questions / future work

- Padded-canvas variant of the mark (mark in larger canvas with safe-area padding, for iOS/Android app icon contexts that expect padding): not yet produced, produce if/when app icon submission requires it.
- ICO favicon file (vs just PNG favicon): not yet produced, produce when setting up website favicon.
- Alternate horizontal lockup with mark flipped (and its implications): tabled, do not pursue without revisiting the canonical-orientation decision.
