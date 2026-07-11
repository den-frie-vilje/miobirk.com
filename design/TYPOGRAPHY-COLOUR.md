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
