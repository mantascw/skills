# skills

Agent skills by [@mantascw](https://github.com/mantascw).

## Install

```bash
npx skills add mantascw/skills
```

Or just the one:

```bash
npx skills add mantascw/skills --skill landing-page
```

Works with Claude Code, Codex, Cursor, OpenCode and [others](https://github.com/vercel-labs/skills#supported-agents).

## Skills

### `landing-page`

Builds a one-page landing site through a guided intake instead of a single thin prompt.

Type `landing page` and the agent will:

1. Ask what the page is about, and hold out for 3–4 real sentences — subject, audience, core message, action, tone.
2. Ask for at least three references, fetch them, and ask what specifically you like about each.
3. Ask about typefaces, palette and motion libraries. Optional — skip it and the agent proposes.
4. Propose **three** distinct directions with structure, composition, type, colour, motion, imagery and stack. No code until you pick one.
5. Build it with real content and real images, run it, screenshot it, and run a design review.
6. Hand it back with specific things worth tweaking, rather than declaring it finished.

The design review uses the [`frontend-design`](https://github.com/anthropics/skills) skill when it's installed, and falls back to a built-in anti-generic checklist when it isn't.

## Background

Grew out of a talk, *Same Building, Different Name*, on why AI-generated landing pages all look the same — and what you have to put into the prompt so they don't.

## License

MIT
