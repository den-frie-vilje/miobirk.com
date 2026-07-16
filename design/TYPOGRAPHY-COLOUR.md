# Typography and colour research for round 3

Deep-research pass run 2026-07-10 (fan-out search, source fetch, adversarial
verification; 107 agents). Verified findings below with sources; where
verification came up empty (spacing numerics, flag values) the values are
filled from the standard references and marked as such.

## Typefaces (verified)

- **Fraunces** (Undercase Type, OFL) is the strongest expressive-but-serious
  open display serif for this brief: variable with opsz 9–144, wght 100–900,
  plus SOFT and WONK axes. The optical-size axis is engineered, not
  decorative: as opsz falls, x-height rises, spacing opens, widths expand,
  and the wonky alternates auto-disable at opsz ≤ 18. One family covers
  display (high opsz, heavy, wonk on) and standfirsts (low opsz, calm).
  Source: github.com/undercasetype/Fraunces.
- **Newsreader** (Production Type for Google Fonts, OFL) is the body
  counterpart: wght 200–800, opsz 6–72, designed for continuous on-screen
  editorial reading, with an unusually low opsz floor for captions.
  Source: api.fontsource.org/v1/variable/newsreader.
- Both cover Danish (æ ø å) fully. Both self-host via @fontsource.
- **Queer type culture, verified state:** the institutional centre is the
  Bye Bye Binary collective and its typothèque of post-binary faces; also
  Velvetyne's Velvelyne, Nat Pyper's "A Queer Year of Love Letters",
  GenderFail's protest fonts, Vocal Type. Crucially, the most explicitly
  queer faces are NOT OFL: Velvelyne and the typothèque carry the CUTE
  licence (ethical conditions, no use by big companies), GenderFail grants
  commercial rights by identity. They inform the design but cannot ship
  under this project's unrestricted open-source rule. Their post-binary
  glyph systems target French inclusive writing, not Danish.
- **The governing critical frame** (Paul Soulellis, "What is queer
  typography?", TDC 2021): queer typography is a practice, not a style;
  "there is no queer typography, only queer acts of reading and writing"
  (Nat Pyper's formulation); rainbow type and corporate-pride aesthetics
  are explicitly rejected. Consequence: no typeface is "queer"; queerness
  lives in editorial voice, honesty devices, and a considered palette.
  Source: soulellis.com/wiqt.

## Spacing (from the standard canon; verification pass returned nothing)

Filled from Butterick's Practical Typography, Bringhurst, and web.dev:

- Body: 16 to 19px equivalent, line-height 1.45 to 1.55 (Butterick's 120 to
  145% of point size, web-adjusted), measure 60 to 70 characters
  (Bringhurst's ideal 66).
- Display: line-height 1.0 to 1.1, letter-spacing -0.01em to -0.025em at
  large sizes; optical size does part of this work when the face has opsz.
- Uppercase and small-caps runs: +0.05em to +0.12em tracking, never tracked
  lowercase.
- Scale: a modular scale between 1.25 (major third) and 1.333 (perfect
  fourth) for editorial hierarchies; fluid sizes via clamp() between
  breakpoint anchors.
- Rhythm: an 8px-based spacing scale (0.5rem steps) with em-based leading.

## Display-P3 and pride colours

Verified engineering:

- P3 is a superset of sRGB, roughly 50% larger by gamut volume, expansion
  concentrated in greens and magentas/oranges; authored as
  `color(display-p3 r g b)`; Baseline in all major browsers since May 2023.
- Fallback practice: (1) double declaration, sRGB first, P3 second, on the
  same property; (2) `@supports (color: color(display-p3 1 1 1))` gating,
  mandatory when colours live in custom properties (an unresolvable var()
  is invalid at computed-value time); optionally behind
  `@media (color-gamut: p3)`.
  Sources: webkit.org/blog/10042, developer.chrome.com/docs/css-ui/migrate-hd-color.
- Neon accents belong on non-text elements (rules, highlights, hover
  states, marks) or as grounds under dark ink text; neon as small text on
  light grounds fails WCAG. Near-black and off-white grounds make P3 neon
  read as intentional rather than loud.

Canonical flag values (standard record; the bi flag matters most here):

- Bisexual pride (Michael Page, 1998): pink `#D60270`, purple `#9B4F96`,
  blue `#0038A8`, in 2:1:2 stripes. The purple stripe is defined as the
  overlap of pink and blue: between the categories. For a book called
  "Når biseksuelle lander mellem to stole", the purple-as-overlap is not
  decoration, it is the argument.
- Trans pride (Monica Helms): `#5BCEFA`, `#F5A9B8`, white.
- The design mapping adopted for round 3: the bi triad becomes the site's
  register system. Blue carries research (fagfællebedømt), pink carries
  poetry and the literary, purple carries everything that lands between:
  formidling, essays, and the book itself.

## P3 working palette for round 3

Each accent has a hand-picked sRGB fallback and a P3 form; AA-checked
darker text variants exist for every accent used on light grounds.

| Token | sRGB fallback | display-p3 | Use |
|---|---|---|---|
| rosa-neon | `#F20587` | `color(display-p3 0.937 0.02 0.494)` | rules, marks, hovers, dark-ground accents |
| lilla-neon | `#A928E8` | `color(display-p3 0.63 0.19 0.92)` | rules, marks, hovers, dark-ground accents |
| blaa-neon | `#0A47F5` | `color(display-p3 0.05 0.28 0.96)` | rules, marks, hovers, dark-ground accents |
| rosa-tekst | `#B8005F` | – | AA text on paper (≥ 5:1) |
| lilla-tekst | `#7C3AA0` | – | AA text on paper (≥ 5:1) |
| blaa-tekst | `#1C3FC7` | – | AA text on paper (≥ 5:1) |

Flag-canonical values (`#D60270`, `#9B4F96`, `#0038A8`) are reserved for
the one place the flag itself is quoted (the tri-stripe rule device).

## The action colour (added after Ole chose Overlappet)

Ole pointed to reload.dk as reference and asked for a green or yellow neon
to complement the triad. Reload's measured system (their site.css tokens)
is Space Grotesk and Space Mono on a warm near-black `hsl(32 25% 10%)`,
warm cream, and one loud warm yellow `hsl(51 100% 65%)` doing the action
work, with blunt Danish microcopy. Yellow was chosen over green: it is the
Danish register, and it stays clear of the trans-flag pastel field that a
soft green-adjacent palette could drift towards.

| Token | sRGB fallback | display-p3 | Use |
|---|---|---|---|
| gul | `#FFDE33` | `color(display-p3 1 .88 .15)` | actions only: the primary button (ink text, 13.2:1), hover underlines, nav hover, ::selection. Never as text, never as a register. |

The semantic split keeps the triad's fence intact: the triad says what
things are (registers of her work); the yellow says what you can do.

## Typography revision (Ole, 2026-07-10): reload's system verbatim

Ole judged the offset-shadow buttons horrible and asked to copy reload.dk's
typography and buttons outright. From reload's site.css tokens: headings
and body in Space Grotesk 400 (headings letter-spacing 0, line-height
1.3em; body 1.5em); the functional layer (nav, labels, metadata, buttons)
in Space Mono 400; primary button solid square yellow, no border, Space
Mono 400 uppercase, letter-spacing .1em, line-height 1em. The yellow was
retuned to reload's own darkAccent, hsl(50.85 100% 65.29%) = #FFE04D,
P3 color(display-p3 1 .89 .35); ink on it measures 12.6:1. Fraunces and
Newsreader are retired from the direction; Space Grotesk and Space Mono
are both OFL and self-hosted via @fontsource in production. The earlier
research on Fraunces/Newsreader stands as record of the road not taken.

## The illustration layer (from the book itself, 2026-07-11)

The book PDF (designed by Ole, per its colophon) settles the illustration
question. It is set in Palatino, Avenir Next, and Typefesse (Océane Juvin,
Velvetyne Type Foundry, OFL), and Typefesse is its illustration system:
the cover title shadows itself in offset Typefesse over a bi-gradient, and
interior pages carry oversized, cropped Typefesse glyphs stroked in a
pink-to-purple-to-blue gradient as full-page vignettes.

The site copies that treatment rather than inventing one: the real cover
(rendered from the PDF, design/assets/omslag.png) replaces the CSS
stand-in, and Typefesse Pleine and Claire-Obscure (woff2 in
design/assets/fonts/, OFL, from velvetyne.fr) provide oversized
overlapping background vignettes in the hero and small margin vignettes
beside sections, filled with the triad gradient
(rosa 0%, lilla 48%, blaa 100%). Vignettes are aria-hidden, pointer-inert,
and hidden on narrow viewports where they would sit behind text.

Two corrections the book forced: the subtitle is "Når biseksuelle falder
mellem to stole" (the site's own list had said "lander"; the cover, title
page and colophon all say "falder", and the book governs), and the
Offerfonden formula is now known verbatim from the colophon and appears in
the book section: "Dette materiale er støttet økonomisk af Offerfonden.
Materialets udførelse, indhold og resultater er alene forfatterens ansvar.
De vurderinger og synspunkter, der fremgår af materialet, er forfatterens
egne og deles ikke nødvendigvis af Rådet for Offerfonden."

## Titles in serif (Ole, 2026-07-11)

Titles moved to serif. The book supplies which serif: it is set in
Palatino, and the libre Palatino is TeX Gyre Pagella (GUST e-foundry,
free GUST Font License, vendored as OTF in design/assets/fonts/). Final
type system: titles and standfirsts in TeX Gyre Pagella (400 for display,
700 for list-size titles, italic for standfirsts and bylines); body in
Space Grotesk 400 (reload.dk); functional layer and buttons in Space Mono
400 (reload.dk); Typefesse as the illustration layer. Note the Pagella
licence is GUST/LPPL-derived rather than OFL: free and redistributable,
recorded here as a conscious deviation matching the book's own typography.

## Typefesse variant research (Ole's request, 2026-07-11)

From Velvetyne's own specimen text (Océane Juvin): Typefesse's three
styles are named after the moon. **Claire** is the most agile and
contorted, bodies twisting to fit inside the letters, and when set
together the letters "snuggle against each other". **Obscure** is the
most graphical and illustration-like, the alphabet as "lock holes"
through which the reader sees the backside of letters. **Pleine** is the
heart of the letters, the most readable, and is explicitly designed to
"be used as an additional layer on top of the Claire and Obscure
styles". The two shipped files encode this: Typefesse Claire-Obscure
sets capitals in Obscure and lowercase in Claire; Typefesse Pleine is
the solid layer. The intended interplay is chromatic layering: Pleine in
one colour with Claire or Obscure superimposed in another.

Charset, measured from the shipped woff2 cmaps (173 glyphs): basic Latin
plus Western European accents; **no æ, ø, Æ or Ø** (å and Å exist).
Vignettes therefore use base Latin characters only.

The site's implementation, final form: the background spells TIGER,
her middle name, down the page in five huge letters (61 to 91rem),
positions from a seeded random scatter (seed 2026), overlapping, drawn
entirely in shades of the paper: solid Pleine a step off the ground
(#F4EFE3 / #F6F1E7), Claire/Obscure outline a step deeper (#E9E1D0 /
#ECE5D6), offset like the book cover's shadow play. They read as
watermarks; ink text stays legible above every letter. Two depth
layers parallax at 0.10 and 0.22 of scroll speed; static without
JavaScript and under prefers-reduced-motion. Separate from the
parallax, the hero carries its own pair: two partially overlapping
outline-only Claire-Obscure glyphs at medium size (16 to 19rem) in the
full triad gradient, with no solid layer.

## The liquid-chrome hero, retired but kept as method (2026-07-15)

Ole retired the mercury pair and the hero vignettes the same day the
pair was finished: a fun experiment that worked, dropped from the
direction, with the method noted for later. The section below stands
as that note; the vendored three.js in `design/assets/vendor/` stays
for the day the technique is wanted again (a launch moment, a book
page easter egg, a talk visual). What replaced it is the hand-drawn
layer described in "The hand" below.

Ole asked for the hero glyph as a three-dimensional shape in the
liquid, mercurial drip register of contemporary queer club graphics,
with a holographic sheen. The form arrived over three passes of his
direction: a first extrusion of Typefesse Pleine's solid m read as a
molten plate, so the outline cut replaced it (poured metal tracing the
letter); then the material was turned up and the b returned, so the
shipped object is the pair from the original hero, intertwined in
three dimensions. Each letter is Typefesse Claire's stroke band (the
glyph's outer envelope with the solid letter subtracted), extruded
shallow with a rounded bevel; the m stands ahead, the b threads behind
and through it with its own tilt, and the two counter-sway so the
ribbons keep crossing.

- The glyph contours are extracted from the woff2 with fontTools and
  inlined as path commands, with contour nesting (which contour is a
  hole of which) computed offline by containment depth; three.js
  winding detection guesses wrong on these glyphs. `ExtrudeGeometry`
  gives the bands depth; vertices are welded by position so each
  surface reads as one skin.
- The mercury is `MeshPhysicalMaterial` at full metalness, low
  roughness, with the thin-film `iridescence` parameters carrying the
  holographic sheen. The environment map is procedural: a canvas of
  silvery gradient bands (a bright chrome horizon) with vertical
  streaks of the triad and a restrained trace of the action yellow, so
  the reflections are literally the site's own palette. After Ole
  asked for a louder material the streaks widened to cover most of the
  horizon and the iridescence range and envMapIntensity rose; the
  ribbons now carry visible runs of blue, pink and gold rather than
  plain silver.
- Motion: a simplex-noise field displaces vertices along their
  normals, biased toward the letters' feet so the lower runs of the
  ribbons slump and sway (gentle; thin bands distort fast); five
  chrome beads swell at the feet of both letters and fall as drips on
  offset cycles. The pair sways as a group while each letter
  counter-rotates slightly against it.
  Static single frame under prefers-reduced-motion; paused offscreen
  via IntersectionObserver; pixel ratio capped at 2.
- Fallbacks: without JavaScript or WebGL the overlapping outline-only
  gradient pair (m and b, Claire-Obscure) remains in the same
  position. On narrow viewports the pair gets a reserved band above
  the text rather than sitting behind it, so ink never crosses the
  chrome.
- three.js r178 is vendored (MIT, `design/assets/vendor/`); modules
  need HTTP, so the screenshot runner now serves the design directory
  over localhost instead of file://.

## The hand (Ole, 2026-07-15)

The hero and the masthead moved from type to a hand. Both are inline
SVG drawn with a monoline round-capped stroke and animated on load
with one pure-CSS technique: every path carries `pathLength="1"`, so
`stroke-dasharray:1` plus a dash offset animated from 1 to 0 draws
the stroke; two custom properties per path (`--d` duration, `--t`
start) sequence the strokes like a writing hand. No JavaScript, so
the drawing runs everywhere, including surfaces that strip scripts.
Static final state under prefers-reduced-motion.

- **The hero title is a tag.** "Ikke bare køn" written as a
  handstyle tag (stroke 13 in an 880-unit viewBox, leaning through
  rotate(-2deg) skewX(-8deg)), drawn in about 1.6 seconds. It took
  three of Ole's corrections to get here: the first pass was neat
  print letters (too cute), the second was print letters with flicks
  (still not a tag). What finally reads as a tag is that the words
  are WRITTEN, not lettered: ten strokes in total, whole words
  running continuously with the pen lifting only where a real hand
  lifts (the k arms as separate "<" cuts, the slash of the ø, the
  return underline). "bare" is one unbroken stroke. "køn" is one
  unbroken stroke including the exit whip off the n. The underline
  is the hand coming back right to left under the whole line. The
  lesson for future hand-drawn work: tag-ness lives in stroke
  economy and connection, not in adding flicks to print letters.
  The emphasis on "bare" is a change of style inside the writing:
  the word is larger, looser and pressed harder (stroke 15).
  Nothing is added. The h1 keeps a visually-hidden text node, so
  semantics and search read "Ikke bare køn" as before.
- **No wordmark in the masthead.** In its place a very simple tiger
  (her middle name) in the same pen. The first pass read as a cat:
  pointed ears and whiskers are cat signals. The redraw uses the
  tiger's own cues instead: small round ears, three forehead
  stripes, two bold stripes entering from each side, slanted eyes.
  Sixteen strokes, the home link, aria-labelled, drawn in about a
  second.
- A first pass drew "Mio Birk" as a signature tag in the masthead;
  Ole redirected the tag to the hero text and replaced the masthead
  wordmark with the tiger. The signature paths live in this
  repository's history should a signature ever be wanted (colophon,
  about page).
