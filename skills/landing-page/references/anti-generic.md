# Anti-generic review checklist

Fallback for when the `/frontend-design` skill isn't installed. That skill is more thorough — suggest it once, then use this.

Walk the built page and check each item honestly. For anything that fails, change it and say what you changed.

## The tells

Current AI-generated pages cluster hard. If the page hits several of these, it will read as machine-made regardless of how clean the code is.

- Cream background (around `#F4F1EA`) with a high-contrast serif display face and a terracotta accent (around `#D97757`).
- Near-black background with one acid-green or vermilion accent.
- Content chopped into identical rounded cards, one border-radius on everything, the same soft grey shadow under each.
- Gradient washes used as decoration rather than to carry meaning.
- Tracked-out ALL-CAPS eyebrow labels above every heading.
- Meta strings joined with middle dots: `A · B · C`.
- `WORD — fragment` labels with a spaced em dash.
- Tinted near-black (`#0B0B0B`, `#111`) standing in for black.
- A monospace face used for small data labels for no reason.
- `→` appended to link and button text.
- Numbered markers `01 / 02 / 03` on content that isn't actually a sequence.
- One word in the headline italicised, bolded, or coloured differently.

Any of these is fine if the brief asked for it. The problem is reaching for them when the brief left the axis free.

## Hero

The hero is the whole first impression. Open with the most characteristic thing in the subject's world — an image, a word, an animation, a live demo — not with a big number and a gradient, which is the default treatment.

Ask: if you swapped the text for a different subject entirely, would the hero still work? If yes, it isn't about this subject.

## Typography

- One family, or two that are clearly distinct. Not three.
- Not Inter, not the face you'd reach for on any project. Choose deliberately.
- A real type scale with intentional weights and spacing, not four sizes picked by feel.
- Line length under 80 characters. Serif body text gets slightly more line-height than sans.
- If type is acting as a headline or a visual element, make the treatment itself part of the design.

## Structure

Borders, rules, numbers, eyebrows and dividers should encode information about the content. If a device is only there to fill space, remove it.

## Motion

- One orchestrated moment beats scattered effects. A single page-load sequence or one reveal.
- Fade-and-slide-up on every section, plus a hover transition on every card, is the generic default.
- Motion that responds to a user action — opening, expanding, confirming — is always welcome.
- `prefers-reduced-motion` must be respected.

## Copy

- Plain verbs, sentence case, no filler.
- Active voice. A button says what happens: "See the exhibition", not "Learn more".
- Written from the visitor's perspective, in words they already use.
- Each line does exactly one job.

## The last pass

Chanel's rule: before leaving the house, look in the mirror and remove one accessory.

Spend the boldness in one place. Let one element be the memorable thing and keep everything around it quiet. Then find the one decoration that doesn't serve the brief, and cut it.
