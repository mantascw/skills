# Where to find materials

For people who don't do design and need somewhere to start looking.

## One rule

**Raw material, not finished appearance.**

A font file, a photograph, an easing curve are ingredients. What you do with them is yours.

A styled component kit, a stock photo, a generated palette, a template — these arrive already looking like something. That something is what everyone else's page looks like, because they all started from the same box. The page comes out as the average of everything the source has ever produced.

Everything below is raw material. The popular exceptions are named at the bottom, with what they cost you.

---

## Type

The single biggest lever on how a page feels. Change nothing else and change the typeface, and it's a different page.

- **[Fontshare](https://www.fontshare.com)** — free for commercial use, variable weights, properly drawn. Note that Satoshi and Clash Display are the two most-downloaded faces in the catalogue by a wide margin; they're well on their way to becoming the next Inter. Use the rest of the library.
- **[Fonts In Use](https://fontsinuse.com)** — an archive of typefaces in real projects. The hard part isn't finding a font, it's knowing what it looks like deployed. Search a face here before you commit to it.
- **[Fontsource](https://fontsource.org)** — self-host open fonts as npm packages. Faster than a Google Fonts link and no third-party request.

For pairing: one family, or two that are clearly distinct. Two faces that are nearly the same read as a mistake.

## Motion

- **[GSAP](https://gsap.com)** — the standard for scroll-driven work. Fully free since April 2025, including every formerly paid plugin: ScrollTrigger, SplitText, MorphSVG, ScrollSmoother. If you were told ScrollTrigger costs money, that's out of date.
- **[Motion](https://motion.dev)** — formerly Framer Motion. The React answer; Motion One covers vanilla JS.
- **[Lenis](https://lenis.darkroom.engineering)** — smooth scroll, small and well-behaved. GSAP's ScrollSmoother does the same job if you're already using GSAP.
- **[CSS scroll-driven animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll-driven_animations)** — native, no library. Enough for reveals and progress indicators. Reach here first.
- **[easings.net](https://easings.net)** — the curve matters more than the duration. Default `ease` is why motion feels cheap.

Respect `prefers-reduced-motion`. Not optional.

## Imagery

Public-domain archives beat stock. The material is more specific, more surprising, and free of the look that makes a photo recognisable as stock.

- **[Met Open Access](https://www.metmuseum.org/art/collection)** — ~500k public-domain works, high resolution.
- **[Rijksmuseum](https://www.rijksmuseum.nl/en/rijksstudio)** — exceptional scans, generous download sizes.
- **[Smithsonian Open Access](https://www.si.edu/openaccess)** — ~4M items, far beyond art.
- **[Library of Congress](https://www.loc.gov/free-to-use/)** — photography, maps, ephemera, print.
- **[Wikimedia Commons](https://commons.wikimedia.org)** — everything else. Check the licence on each file and credit as required.

Credit in the markup even when the licence doesn't demand it.

## Craft

- **[Utopia](https://utopia.fyi)** — fluid type and space scales that interpolate between breakpoints. Solves most of what goes wrong between 390 and 1440 in one step.
- **[Squoosh](https://squoosh.app)** — compress images properly. An uncompressed hero is the most common performance problem on a landing page.

If the page genuinely needs an accordion, a dialog or a form, use unstyled primitives — [Base UI](https://base-ui.com) or [Radix](https://www.radix-ui.com/primitives) — and write the CSS yourself. Never a styled kit.

## Inspiration

Places to go and get the three references this skill asks for in Step 2.

- **[Mobbin](https://mobbin.com)** — real product UI, searchable by pattern.
- **[SiteInspire](https://www.siteinspire.com)** and **[Godly](https://godly.website)** — curated web design, strong on type and motion.
- **[Are.na](https://www.are.na)** — slower, stranger, better for finding something that isn't already in everyone's moodboard.

Collect the mechanism, not the vibe. "The name is enormous and the image under it is small" is usable. "Clean and elegant" is not.

---

## The popular ones, and what they cost

Not forbidden. Just understand what you're buying.

| | |
|---|---|
| **Google Fonts** | Fine, and the most-used faces on the web are in it. Inter, Poppins and Montserrat are instantly legible as defaults. Fontshare costs the same (nothing) and doesn't. |
| **Unsplash / Pexels** | Free, but stock photography has a recognisable look — the same compositions, the same lighting, the same empty laptop on the same desk. The top results have been used thousands of times. |
| **Coolors** | Generates a palette with no knowledge of your subject. Useful for exploring relationships, not for choosing. |
| **shadcn/ui** | Pre-styled Tailwind components. Fast, popular, and the direct source of the identical-rounded-cards look. It's a look, and it's a common one. |
| **Tailwind defaults** | The utility layer is fine. The default scale is where `rounded-lg` + `shadow-md` + `gray-500` comes from — override it. |

The common thread: each saves a decision, and the decision it saves is one of the few that makes the page specific to its subject.
