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
