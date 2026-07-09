# Critique round, 2026-07-09

The first iteration of the three mockups was reviewed by two independent
critique agents: an art and design critic (composition, typographic craft,
colour, queer design history) and a literary and editorial critic (whether the
design reads Mio correctly, Danish typographic convention, honesty of labels
and copy). This file records their verdicts and what was changed in response.
The full critiques live in the session record; the git diff of the refinement
commit shows every applied fix.

## Shared findings, applied to all three

- **The book headline logic was wrong.** All three led with "Hvorfor lander
  biseksuelle mellem to stole?", converting her descriptive subtitle ("Når
  biseksuelle lander...") into a causal promise in content-marketing grammar.
  Fixed: the title *Tvivlen Skygger for Trygheden* now leads, with her exact
  subtitle as standfirst, and her full sentence "Bogen er især henvendt til
  dig, der arbejder med at forebygge diskrimination og vold, men alle kan
  læse med" restored where it had been clipped.
- **Genre labels under-delivered.** "Forskning" and "Artikel" conflated
  register and form, and nothing said peer-reviewed. New label set:
  Bog, Fagfællebedømt, Formidling, Essay, Digt.
- **Title and venue fidelity.** Her published title case is used verbatim
  everywhere; "Magasinet Slagtryk" corrected to "Slagtryk".
- **Danish punctuation.** Spaced en-dash (tankestreg) in bylines and
  signatures; the "// name" code-comment signature removed.
- **Fonts must be self-hosted in production** (sovereignty principles); the
  mockups note this and production will use @fontsource packages.

## Retning 1: Lavendel

Art critic: "the most finished and the least brave"; period-prop pile-up
(drop cap + fleuron + asterism) tips into pastiche; centred body text on
mobile violates the direction's own legibility rule; small caps everywhere
flatten hierarchy. Literary critic: the only direction that knows Danish
guillemets exist, but the blockquote silently dropped "derfor" from her
thesis; "you cannot edit an author inside her own quotation marks on her own
site".

Applied: quotation restored verbatim; fleuron and asterism deleted (drop cap
kept); mobile body text left-aligned; nav and buttons set in normal case so
small caps are reserved for section and genre labels; masthead sub no longer
duplicates the hero and now reads "Kønsforsker · Formidler · Digter"; cover
shadow replaced with a hairline border and soft shadow.

## Retning 2: Arkivet

Art critic: "the strongest piece of graphic design of the three"; the
destabilised BARE is "a genuinely intelligent typographic reading of her
argument"; but the lockup's right edge was untuned, mobile hid table columns
while leaving their headers orphaned, and the mono sizes fell below comfort.
Literary critic: the desktop publication table is "the most honest
presentation of her range anywhere in the set", but the tag chips turned a
public-interest book into a SKU, the cover accent celebrated the wrong word
(trygheden, the thing being lost), "EST. 2019" was streetwear branding
applied to a person, and the contact headline dropped the poet.

Applied: tag chips deleted; cover accent moved to TVIVLEN; lockup tuned to a
shared right edge; the mobile table restacks as card rows so year, genre and
venue survive at every viewport; mono floored at .8rem and the Offerfonden
credit set in sentence case at .85rem; "PH.D. 2019 · AARHUS UNIVERSITET";
contact headline now "Forsker, formidler, digter"; "ET ARKIV OVER" removed
from the kicker; both magentas defined as one accent with a light variant
for ink grounds.

## Retning 3: Bevægelse

Art critic: "the most seductive screenshot and the most derivative design";
the gradient italic gesture appeared seven times and the pill button,
gradient card border and blob idiom read as this year's product-site
template. Literary critic: "the only direction whose form makes her
argument", but a comma error sat in the largest text on the page, "Mellem
*to* stole" stressed the number of chairs, and the manifesto bolded her
thesis like a brand callout.

Applied: the gradient is now reserved for the single word "bevægelse";
every other accent demoted to plain italic in cream; pill button replaced
with a square-cut cream button; cover border is a plain hairline; comma
error fixed; emphasis corrections throughout; contact statement is a real
h2; publication hover no longer reflows (inset rule instead of padding
shift); the ambient dusk now spans the document rather than the viewport;
the mobile header stacks properly and the hero regained its side padding.

## Comparative verdicts

The two critics split, which is itself information. The art critic ranked
Arkivet strongest as-is (form argues the content; faults were mechanical)
with Bevægelse holding the most unrealised potential. The literary critic
recommended developing Bevægelse (the only direction where the layout says
what she says) with Lavendel's discipline imported, and advised declining
Arkivet as a governing metaphor while mining its publication table, since an
archive fixes what her thesis insists is in motion. Both agreed Lavendel is
the safe, credible, finished pick with the lowest ceiling.

The choice between directions is Ole's and Mio's; all three are now refined
to the point where the choice is about temperament, not craft.
