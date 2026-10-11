---
name: landing-page
description: Build a distinctive one-page landing site through a guided intake — topic and core message, three or more references, optional style and motion direction, then three design directions proposed before any code is written. Use when the user writes "landing page", or asks to design or build a landing page, hero section, promo page, or marketing one-pager.
metadata:
  author: mantascw
  version: "1.0.0"
---

# Landing Page

Most AI-built landing pages look identical because the prompt was thin. One sentence in, one template out. This skill spends the first few minutes gathering a real brief, proposes three directions, and only then writes code.

The intake is the product. Do not rush it.

---

## Ground rules

These apply to every step below.

- **One step per turn.** Ask, stop, wait for the answer. Never bundle two steps into one message.
- **The gates are real.** Steps 1, 2 and 5 have a bar that must be met before moving on. Do not advance because the user seems impatient — advance because the bar is met.
- **No code before Step 5 is approved.** Not a scaffold, not a quick sketch, not "just the hero to show you". Nothing.
- **Don't echo the user back.** A short reaction is fine. Summarising their own words at them wastes their time.
- **Open questions get plain text.** Use structured multiple-choice only when the user is genuinely picking from a list.
- **Keep your own questions short.** One paragraph of ask, not a form.

---

## Step 1 — Topic and core message

Ask what the page is for. Tell the user you want 3–4 sentences, not a title, and say why: the difference between a generic page and a good one is almost entirely in this answer.

Prompt them to cover the subject, who it is for, and what a visitor should take away or do.

**Gate — do not continue until you can state all five of these in one sentence each:**

| | |
|---|---|
| Subject | What the page is actually about |
| Audience | Who lands on it, and what they already know |
| Core message | The one thing they must leave with |
| Action | What they should do, or feel, by the end |
| Tone | How it should feel — calm, loud, technical, playful |

If something is missing, ask **one** follow-up at a time, naming the specific gap. Maximum three follow-ups; after that, propose your own answer for whatever is still open and ask the user to confirm or correct it.

Hold this brief in mind for the rest of the session. Every later decision gets checked against it.

---

## Step 2 — References

Ask for at least three references, in any form:

- Live URLs of sites they like
- Screenshots or images of a hero, a layout, a type treatment
- A Figma file or a local image path
- A description precise enough to find ("that Apple product page with the scroll-driven zoom")

For each reference, ask what specifically they like about it — composition, typography, motion, density, colour. "I like this site" is not usable; "I like how the hero holds one image and nothing else" is.

**Actually look at them.** Fetch URLs and read the structure. Open image files. Do not take the user's word for what a reference contains.

**Gate — three usable references with a stated reason each.**

If the user can't reach three after two asks, don't stall. Propose five candidate references yourself, drawn from the Step 1 brief, and ask them to pick at least three and say what appeals. Picking is easier than recalling.

---

## Step 3 — Style and tools (optional)

Ask whether they have constraints or preferences already in mind:

- Typefaces, or a foundry/vibe they want
- Colour palette, brand colours, things to avoid
- Motion: GSAP + ScrollTrigger, Framer Motion / Motion One, Lenis for smooth scroll, or no motion at all
- Anything they must or must not use — a component library, an existing design system, a deployment target

This step is genuinely optional. If the user has nothing, say you'll propose a direction for each of these in Step 4 and move on immediately. Don't interrogate.

---

## Step 4 — Three directions, no code

Present exactly three directions. They must be meaningfully different — not one idea in three colourways. Vary the structural idea, not just the palette.

For each direction give:

- **Name** — short, memorable, so the user can say "let's do the second one"
- **Concept** — one line on the idea and why it fits the brief
- **Structure** — the sections in order, with what each one does
- **Composition** — the layout idea, with a small ASCII wireframe of the hero
- **Typography** — the actual typefaces, their roles, and why these and not the usual ones
- **Colour** — 4–6 named hex values
- **Motion** — what moves, when, and why. If nothing should move, say so
- **Imagery** — what images the page needs and where they come from. Flag anything the user must supply
- **Stack** — what you'd build it in, and the reason
- **The risk** — the one thing that makes this direction distinctive, and what it costs

Before showing them, check each direction against the brief from Step 1. If any part of it would read the same for a different subject entirely, it's a default rather than a choice. Replace it.

End by asking the user to pick one, or to mix elements across directions. Wait.

**Gate — an explicit choice. "They all look good" is not a choice; ask them to pick.**

### Choosing the stack

Let the brief decide, not habit.

- Scroll-driven, motion-heavy, no data or routing → a plain Vite + HTML/CSS/JS setup. Least framework noise, GSAP and Lenis drop straight in.
- Needs routing, a CMS, forms, or serious SEO → Next.js.
- Already inside an existing repo → match what's there. Never introduce a second framework.
- The user named a stack in Step 3 → use it, no debate.

State the choice and the reason in the direction. Don't make the user ask.

---

## Step 5 — Build

Build the chosen direction.

- **Real content.** Write actual copy from the Step 1 brief. No lorem ipsum, no `[Your headline here]`.
- **Real images.** Use what the user supplied. If they supplied nothing, source public-domain or appropriately licensed images and credit them in the markup. Tell the user exactly which images are placeholders and need replacing.
- **Quality floor, unannounced.** Responsive to mobile, visible keyboard focus, `prefers-reduced-motion` respected, sensible contrast.
- **Run it.** Start the dev server, open the page, screenshot it, and look. Check the hero, mid-scroll, the footer, and a narrow viewport. Fix what looks wrong before showing the user.

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
