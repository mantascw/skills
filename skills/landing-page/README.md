# Landing Page

Build a landing page through a guided intake instead of a single thin prompt. Packaged in the [Agent Skills format](https://agentskills.io/home).

Ask an agent for a landing page and you get the same page every time: centred hero, gradient wash, Inter, three rounded cards, a fade-up on every section. That isn't a model limitation — it's what a one-line prompt deserves. The template is the average of everything, and a thin prompt gives the model nothing to deviate from.

This skill front-loads the part people skip. It holds out for a real brief, makes you produce references and says what it sees in them, proposes a style and stack for you to confirm, and offers three distinct directions. No code is written until you've picked one.

## Install

```bash
npx skills add mantascw/skills --skill landing-page
```

For manual installation, clone the repository and install or symlink `skills/landing-page` according to your tool's skills documentation:

- [Claude Code](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview#using-skills)
- [Codex](https://developers.openai.com/codex/skills/#where-to-save-skills)
- [Cursor](https://cursor.com/docs/context/skills#enabling-skills)

Building and previewing the result needs Node and a terminal the agent can run a dev server in. The intake itself works anywhere.

## Use

> Build a landing page for M. K. Čiurlionis, the Lithuanian painter and composer.

> I need a landing page for our Series A announcement. Here are three sites I like: …

> Landing page for a supper club I run out of my flat. No references, propose some.

Mentioning a landing page is enough to trigger it. You can front-load as much of the brief as you like — the skill will skip what you've already answered and press on what you haven't.

Expect five to ten minutes of back-and-forth before any code appears. That delay is the feature. If you want a page in one shot, don't use this.

## How it works

- **A brief, not a title.** Five things have to be on the table before anything else happens: subject, audience, core message, action, tone. Missing ones get chased one at a time, as multiple choice where the options can be named.
- **References, actually opened.** At least three, in any form — URLs, screenshots, local paths, or a description precise enough to find. The agent fetches them and reads the structure rather than taking your word for what's in them.
- **The tension gets named.** References usually pull in incompatible directions. The agent says what mechanism it sees in each one, then makes you resolve the conflict. That choice tends to be worth more than the brief.
- **Style proposed, not interrogated.** Typefaces, palette, motion, stack and imagery are inferred from what you've already said and handed back as a proposal. One question to confirm, then on.
- **Three directions in prose.** Structurally different ideas, three to five sentences each. No wireframes, no hex codes, no spec tables — detail you can't evaluate yet makes the choice harder, and it gets worked out after you pick.
- **Built, then reviewed.** Real copy and real images, a quality floor that isn't announced, and a design pass against [`frontend-design`](https://github.com/anthropics/skills) when it's installed or the built-in anti-generic checklist when it isn't.
- **Handed back, not declared finished.** You get a running URL and three to five specific things worth changing. Vague follow-ups like "make it pop" are treated as real instructions, not as a failure to specify.

Throughout, choices are offered as multiple choice with a free-text escape, so the typing you do is concentrated in the two places that need your own words.

## What you get

A running dev server, a page built from your brief with real content, and the images credited or flagged as placeholders. The stack follows the brief — plain Vite for scroll-driven work, Next.js when there's routing or a CMS, or whatever is already in the repo.

## References

| File | Use when |
|---|---|
| [SKILL.md](SKILL.md) | The six steps, the gates, and what stops the agent advancing |
| [references/anti-generic.md](references/anti-generic.md) | Reviewing a built page when `frontend-design` isn't installed |

## Background

Grew out of a talk, *Same Building, Different Name*, on why AI-generated landing pages all look the same — and what you have to put into the prompt so they don't.

## License

MIT
