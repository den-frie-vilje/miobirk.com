# Design directions for miobirk.com

Three deliberately different directions for the rebuild, each mocked up as a
self-contained HTML page in `directions/`. All three share the same brief and
constraints; they differ in temperament.

## Shared brief

- Editorial design: the site should read like a well-set publication, not a
  template. Typography carries the identity; there is no logo and no stock
  photography.
- Modern queer, intellectual, bold but elegant. Queerness is carried through
  design history (lavender, zine and archive culture, fluidity) rather than
  rainbow cliché.
- Open-source typefaces only (all chosen faces are OFL-licensed and cover
  Danish æ ø å).
- Legibility first: body measure 60 to 75 characters, generous leading,
  WCAG 2.1 AA contrast, visible focus states, reduced-motion respected.
- Danish content, taken verbatim from the existing site.
- Target stack, decided before design: the chrishemmings.co.uk lineage.
  SvelteKit 2 with Svelte 5 runes, TypeScript, Tailwind CSS v4,
  adapter-static, Sveltia CMS, NAS pull-only deployment. Everything mocked
  here is static-buildable.

## Direction 1: Lavendel (the literary review)

The queer intellectual as essayist. A classical typographic axis, warm paper,
ink, and lavender, the oldest queer colour there is. Reads like a small,
serious European journal that happens to be alive.

- **Type:** Fraunces (display, wonky optical sizes at large settings) with
  Source Serif 4 for text. Letterspaced small caps for metadata.
- **Palette:** warm ivory paper `#F7F2E9`, ink `#211D1A`, lavender
  `#5B4BC4` as the single accent, with a paler lavender wash for grounds.
- **Layout grammar:** centred column, hairline rules, drop cap on the
  manifesto, publications set as a bibliography with hanging indents and
  small-caps genre labels. Roman and italic interplay in display lines.
- **Risk:** could tip nostalgic. The wonk in Fraunces and the saturation of
  the lavender are what keep it contemporary.

## Direction 2: Arkivet (the index)

The body of work as an archive. Queer zine and index-card culture disciplined
by a strict modern grid: full-bleed rules, oversized numbering, a publication
table with year, genre, and venue as first-class columns. The boldest of the
three.

- **Type:** Archivo (variable width and weight; expanded black for display)
  with IBM Plex Mono for metadata, numbers, and tags.
- **Palette:** bone `#EFECE4`, ink `#161411`, signal magenta `#B4005A` as
  the working accent; footer inverts to ink.
- **Layout grammar:** everything on a visible structure. Numbered sections
  (01, 02, 03), tabular publications, sharp corners, no soft shadows. The
  headline IKKE BARE KØN set at poster scale with mixed widths.
- **Risk:** could tip cold or techy. The warmth of the bone ground and the
  editorial care in the table typography are what keep it humane.

## Direction 3: Bevægelse (in motion)

"Køn er altid i bevægelse" taken literally. A dark Nordic dusk, serif italics
that lean and drift, and one gradient of twilight light. The most atmospheric
and the most literary-poetic of the three; poetry sits beside research as an
equal.

- **Type:** Instrument Serif (display, roman and italic in dialogue) with
  Schibsted Grotesk (body), a Scandinavian sans built for news legibility.
- **Palette:** deep indigo night `#131120`, warm cream text `#F1ECE2`, and
  a dusk gradient (peach `#FFB199` through lilac `#C3A8F0`) reserved for the
  moving word and thin arcs of light.
- **Layout grammar:** asymmetric, generous dark space, italic display lines
  where the emphasised word carries the gradient, slow ambient drift in the
  background (disabled under prefers-reduced-motion), publications as quiet
  rows that warm on hover.
- **Risk:** dark sites can slide into portfolio-noir. The literary tone of
  voice and cream warmth are what keep it a publication rather than a
  showreel.

## What to judge the mockups on

Whether each direction (a) sounds like Mio rather than a template, (b) holds
scholarly credibility and queer voice simultaneously, (c) keeps long Danish
text genuinely legible, and (d) is distinct enough from the other two to be a
real choice.
