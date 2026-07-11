# Design directions for miobirk.com, round 3

**Decision (Ole, 2026-07-10): Overlappet (retning 7) is the direction.**
It has since been extended with a neon yellow action colour inspired by
reload.dk (see `TYPOGRAPHY-COLOUR.md`, "The action colour"): the triad
carries what things are, the yellow carries what you can do. Natlæsning
remains a candidate dark scheme; Overstregning's one-mark hero remains an
available variant. Next step: scaffold the SvelteKit site from Overlappet.

Round 2 was declined as tame. Round 3 keeps the structural lessons (claim-led
hero, the free book as primary action, three doors, writing by register,
honest copy) and rebuilds the visual identity on the deep research recorded
in `TYPOGRAPHY-COLOUR.md`: a verified open-source type spine, canonical
spacing numbers, and a palette of Display-P3 neon accents derived from the
bisexual pride flag.

## Shared system (all three directions)

- **Type:** Fraunces for display (opsz high, wght 560 to 750, WONK on at
  headline sizes) and Newsreader for text (opsz auto, wght 400 to 500),
  both OFL, both variable, self-hosted in production via @fontsource.
- **Spacing:** body 1.125rem at line-height 1.5, measure 60 to 70ch;
  display line-height 1.02 to 1.08 with -0.015em tracking; uppercase runs
  +0.08em; modular scale ~1.29; 8px rhythm.
- **Colour:** the bi pride triad as the site's register system, not as
  decoration. Blue carries research, pink carries poetry, purple carries
  what lands between: formidling, essays, and the book. Neon accents are
  authored in Display-P3 with hand-picked sRGB fallbacks behind @supports;
  AA-checked darker variants exist for any accent used as text on light
  grounds. The flag-canonical values appear in exactly one device: a
  2:1:2 tri-stripe rule, the flag quoted rather than worn.
- **The triad's fence (from the round-3 critique):** a colour appears only
  where a genre word anchors it (the publication list, the register key)
  or where the overlap argument itself is made (purple on the book and on
  the site's central phrase). Never one-of-each across doors or sentences;
  interactions stay inside their element's register. Strictly, the purple
  is the argument: it is the flag's own overlap stripe pointed at a book
  about landing between. The blue-research and pink-poetry assignments
  are convention, not flag semantics, and shipping the triad at all is
  Mio's call to make knowingly; she answers for it at seminars, not us.
- **The queer position** (per Soulellis): queerness as practice, not skin.
  The palette is the argument (purple is the overlap between pink and
  blue; her book is about landing between), the voice stays hers, and
  there is no rainbow.

## Retning 7: Overlappet (paper and the triad)

Light. Warm paper, near-black ink with a violet cast, and the three
register colours working structurally through the whole page: coloured
genre labels, neon marks and underlines, the tri-stripe rule under the
masthead. Fraunces at poster scale with wonk on. The most complete
statement of the register system.

## Retning 8: Natlæsning (neon on night)

Dark. Near-black night ground, warm cream text, the triad as glowing neon
on dark, where P3 actually earns its keep. Display type enormous; neon
reserved for large type, rules and marks; body text always cream. The
boldest and most atmospheric. Both round-3 critics concluded it should
not ship as the identity but as the dark scheme of Overlappet
(prefers-color-scheme: dark); it is kept as a mockup so that judgement
can be made against the corrected page rather than an argument.

## Retning 9: Overstregning (the highlighter)

Light, reading-first. The scholar's own practice, marking text, becomes
the design device: neon highlighter swipes behind key phrases (vivid neon
under display-size text, AA tints under small text), Newsreader carrying
long text with Fraunces only at the masthead. The quietest layout with
the loudest single gesture.

## What to judge them on

Whether the neon reads as hers (a researcher of the between) rather than
as trend; whether legibility survives the boldness at every size; and
whether each would beat emmaholten.com on presence without losing the
seriousness a KU professor or a Politiken journalist needs to see.
