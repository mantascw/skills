---
name: landing-page
description: Build a distinctive one-page landing site through a guided intake — topic and core message, three or more references, a proposed style and stack to confirm, then three design directions described in prose before any code is written. Use when the user writes "landing page", or asks to design or build a landing page, hero section, promo page, or marketing one-pager.
metadata:
  author: mantascw
  version: "1.1.0"
---

# Landing Page

Most AI-built landing pages look identical because the prompt was thin. One sentence in, one template out. This skill spends the first few minutes gathering a real brief, proposes three directions, and only then writes code.

The intake is the product. Do not rush it.

---

## Ground rules

These apply to every step below.

- **One step per turn.** Ask, stop, wait for the answer. Never bundle two steps into one message.
- **The gates are real.** Steps 1, 2 and 4 have a bar that must be met before moving on. Do not advance because the user seems impatient — advance because the bar is met.
- **No code before Step 4 is approved.** Not a scaffold, not a quick sketch, not "just the hero to show you". Nothing.
- **Every size, always.** The page works at every breakpoint. This is not a feature, an option, or a trade-off. Never ask the user whether they want it, never offer a desktop-only version, never report it afterwards as though it were an achievement. A design that only resolves on a wide screen is not finished.
- **Don't echo the user back.** A short reaction is fine. Summarising their own words at them wastes their time.
- **Keep your own questions short.** One paragraph of ask, not a form.

### Asking questions

Typing is the main cost the user pays in this skill. Default to **AskUserQuestion** so they can click instead.

Use AskUserQuestion when you are offering a choice between positions you can name — a decision you could make yourself but shouldn't. Every one of these carries a free-text "Other", so the user is never boxed in.

Use plain text only for the two openers that genuinely need the user's own words: the brief in Step 1 and the reference list in Step 2. Everything else — every follow-up, every narrowing, every pick — goes through the modal.

When you build options, make them real alternatives that lead somewhere different. Three sharply opposed options beat four shades of the same answer. Put your recommendation first and mark it `(Recommended)`.

---

## Step 1 — Topic and core message

Ask what the page is for, in plain text. Tell the user you want 3–4 sentences, not a title, and say why: the difference between a generic page and a good one is almost entirely in this answer.

Prompt them to cover the subject, who it is for, and what a visitor should take away or do.

**Gate — do not continue until you can state all five of these in one sentence each:**

| | |
|---|---|
| Subject | What the page is actually about |
| Audience | Who lands on it, and what they already know |
| Core message | The one thing they must leave with |
| Action | What they should do, or feel, by the end |
| Tone | How it should feel — calm, loud, technical, playful |

If something is missing, ask **one** follow-up at a time, naming the specific gap.

Put follow-ups through AskUserQuestion. You have read the brief, so you can almost always name the plausible answers — and seeing them laid out helps the user more than an open question does. Audience is the gap that comes up most:

> **Who lands on this page?** · *Audience*
> - People who've never heard the name — needs context first
> - People who already know the subject — can go straight to the work
> - An art/design audience — wants the work to dominate, minimal narration

Say what changes with each choice. The point is to show the user the consequence, not just collect an answer.

Maximum three follow-ups. After that, propose your own answer for whatever is still open and ask them to confirm it.

Hold this brief in mind for the rest of the session. Every later decision gets checked against it.

---

## Step 2 — References

Ask for at least three references, in plain text, in any form:

- Live URLs of sites they like
- Screenshots or images of a hero, a layout, a type treatment
- A Figma file or a local image path
- A description precise enough to find ("that Apple product page with the scroll-driven zoom")

For each reference, ask what specifically they like about it — composition, typography, motion, density, colour. "I like this site" is not usable; "I like how the hero holds one image and nothing else" is.

**Actually look at them.** Fetch URLs and read the structure. Open image files. Do not take the user's word for what a reference contains.

**Gate — three usable references with a stated reason each.**

If the user can't reach three after two asks, don't stall. Propose five candidates yourself, drawn from the Step 1 brief, in a single AskUserQuestion with `multiSelect: true`. Picking is easier than recalling.

### Name the tension

Once you've looked at everything, tell the user what you think they're responding to — the specific mechanism in each reference, not the vibe. "The artist's name is enormous and the painting under it is small and properly credited" is a mechanism. "Clean and elegant" is not.

References usually pull in incompatible directions, and that conflict is the most useful thing in the whole intake. Name it and make the user resolve it through AskUserQuestion:

> **Your references point two ways — which one?** · *Register*
> - Reverent — the material is treated as precious
> - Irreverent — contemporary handling, deliberately disrespectful of the format
> - The collision — reverent material, irreverent handling

Don't flatten the tension yourself. A user who picks the collision has just given you more than their entire brief did.

---

## Step 3 — Propose the approach, confirm in one question

Do not interrogate. By now you can infer almost all of this yourself, and a list of five open questions about typefaces and motion libraries is exactly the kind of friction that makes people abandon the intake.

Work out your own answer for each of these and state the calls in a short paragraph — the decision and the reason, not a form:

- **Typefaces** — a direction, not a final pick. That lands in Step 4.
- **Colour** — described in words. Note it if the subject already has a palette of its own.
- **Motion** — GSAP + ScrollTrigger, Framer Motion / Motion One, Lenis for smooth scroll, or deliberately none.
- **Stack** — see below.
- **Imagery** — where it comes from, and whether licensing is clear. Flag anything the user has to supply.

Then ask exactly one AskUserQuestion with `multiSelect: true`:

> **Anything to pin down before I draw up directions?** · *Constraints*
> - Nothing — your call (Recommended)
> - I have typefaces or brand colours
> - I have a stack requirement
> - I'll supply the imagery

Anything other than the first option gets one plain-text follow-up for the detail. If they pick the first, move straight to Step 4.

### Choosing the stack

Let the brief decide, not habit.

- Scroll-driven, motion-heavy, no data or routing → a plain Vite + HTML/CSS/JS setup. Least framework noise, GSAP and Lenis drop straight in.
- Needs routing, a CMS, forms, or serious SEO → Next.js.
- Already inside an existing repo → match what's there. Never introduce a second framework.
- The user named a stack → use it, no debate.

---

## Step 4 — Three directions, no code

Present exactly three directions. They must be meaningfully different — not one idea in three colourways. Vary the structural idea.

**Describe each one in prose. Three to five sentences.** The user is choosing between ideas here, not approving a specification, and detail they can't yet evaluate only makes the choice harder.

For each direction:

- **Name** — short and memorable, so the user can say "the second one"
- **The idea** — what the page does, how it's structured, how it behaves as you move through it, and why it fits the brief. Written as prose. Name the typefaces if you have a strong view and say what they're doing. Describe colour in words — "near-black, bone, old gold, a rust accent".
- **The risk** — one line. What makes this direction distinctive, and what it costs. Not a list of caveats, and never "it'll be hard on mobile".

Every direction has to hold up at every size before you propose it. Where an idea needs a different form on a phone — a pinned split becoming a sequence, a horizontal pan turning vertical — that form is part of the direction, worked out before you present it. An idea that only resolves on a wide screen isn't a direction yet, so replace it rather than offering it with a warning attached.

Then ask the user to pick, through AskUserQuestion:

> **Which direction?** · *Direction*
> - *First name* — one line
> - *Second name* — one line
> - *Third name* — one line

"Other" is how they splice elements across directions, so leave room for that in your framing.

**Gate — an explicit choice.**

### What not to do here

- **No ASCII wireframes.** Layout rendered as text characters communicates nothing a sentence couldn't, and reads as filler.
- **No hex codes.** `#C9A227` is not a decision the user can make in the abstract. Say "old gold".
- **No spec tables, no field-by-field template.** Three walls of structured text is harder to choose between than three paragraphs.
- **Don't resolve what you don't need yet.** Exact type scales, palettes and section counts get worked out after the pick, during the build, where they can be seen.

Before showing them, check each direction against the Step 1 brief. If any part of it would read the same for a different subject entirely, it's a default rather than a choice. Replace it.

---

## Step 5 — Build

Build the chosen direction.

- **Real content.** Write actual copy from the Step 1 brief. No lorem ipsum, no `[Your headline here]`.
- **Real images.** Use what the user supplied. If they supplied nothing, source public-domain or appropriately licensed images and credit them in the markup. Tell the user exactly which images are placeholders and need replacing.
- **Quality floor, unannounced.** Visible keyboard focus, `prefers-reduced-motion` respected, sensible contrast, a real `<title>` and meta description.
- **Every breakpoint, from the first section.** See below. Retrofitting small screens after the desktop page is standing is how the second design ends up being a worse version of the first.
- **Run it.** Start the dev server and look at the page at 390, 768 and 1440. Screenshot the hero, mid-scroll and the footer at each width. Fix what's wrong before showing the user, and don't narrate the fixes.

### Breakpoints

Scroll-driven pages don't reflow, they get redesigned. The desktop idea has to survive in a different body, which means deciding what it becomes rather than letting it collapse:

- **Pinned sections** — pinning fights the address bar and eats battery on a phone. Unpin and let the section scroll, or shorten the hold considerably.
- **Horizontal pan driven by vertical scroll** — becomes a vertical sequence, or a swipeable track with real momentum. Not a squashed version of the desktop pan.
- **Split screens** — become a sequence. One register, then the other.
- **Display type** — set for 1440 it is unreadable at 390. Size it with `clamp()` against viewport units so it tracks, and check the longest word in the headline actually fits.
- **Motion** — the same effect count costs far more on a phone. Keep the one piece of motion that carries the idea and drop the rest.
- **Touch** — 44px minimum targets, and nothing important behind a hover.

Pick breakpoints from where this layout actually breaks, not from a framework's defaults. Inherited `sm md lg xl` is the same reflex as reaching for Inter.

### Design review

When the page is standing up, run a design pass:

- If the **`/frontend-design`** skill is available, invoke it and apply its findings. That is the preferred path.
- If it isn't available, apply [references/anti-generic.md](references/anti-generic.md) instead, and mention once that `/frontend-design` gives a stronger review if they want to install it.

Report what the review changed, briefly. Not a list of every tweak — the two or three that mattered.

---

## Step 6 — Hand it back

Never end with "done" or a feature list. The first build is a starting point and the user's taste is the thing that makes it theirs.

Close with:

1. **The URL** of the running dev server.
2. **Three to five specific things worth tweaking**, each named concretely — "the hero type is one size too large on desktop", "the third section needs a real photograph, that one is a placeholder", "the scroll reveal on the gallery fires too early". Not "let me know if you'd like changes".
3. **An open invitation**, in your own words: they should push on it, and you'll make the changes as fast as they can describe them.

If they come back with something vague — "make it pop", "it feels flat" — that is a legitimate instruction, not a failure to specify. Interpret it against the brief, make a confident change, and show them. Don't ask them to define "pop".
