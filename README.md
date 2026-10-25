# Creator AI skill system

**A set of AI skills that produce creator content a human would sign: carousels, posts, comment replies and podcast openings. Every output is checked against its source and against a list of known AI tells before anyone sees it.**

Most AI content reads like AI. It reuses the same sentence shapes, makes up numbers, opens with "Here's the thing" and closes with a recap. Audiences notice within a line, and a brand that posts it looks lazy. This system lets one person run content with AI doing most of the production, while nothing goes out that reads as slop. It is built for any infotainment or educational video channel, or a personal brand.

Built for real client and personal work (details kept private, see "Confidentiality" below). This repository is the public write-up of the approach. It describes the method and the rules, and leaves out the client prompts, data and outputs.

## What a "skill" is here

A skill is a folder of plain-text instructions that an AI agent (Claude Code, in this setup) loads when a request matches it. It holds what to read first, the hard rules, the step-by-step workflow, the checks that must pass, and the exact shape of the deliverable. The agent does the work. The skill decides what counts as finished.

| Skill | What it makes | What keeps it honest |
|---|---|---|
| Carousel director | A ranked set of social carousels from a class transcript or brief, each in a different design from a 32-design library | Every number and quote traced to the source; an independent AI reviewer reads every slide near and far; a human approves before export |
| Writing | Posts, captions, DMs and edits in one person's voice, in English and Hinglish | 36 named AI tells in 8 families, a 50-point score, and a voice profile built only from the person's real posts ([public repo](https://github.com/svx2027/sv-writing)) |
| Comment reply | Four short replies to someone else's LinkedIn post | The reply is about the author's post, never about the user; a scrub list removes lines that read as AI |
| Podcast hook | The cold open and first 3 minutes of a two-person interview cut | Every rule cites an episode and a timestamp from a study of 18 real episodes; a blind re-check agreed with the original coding 96% of the time |
| Retro | Turns each session's corrections into permanent rules | A lesson goes into exactly one file in the project's repo, gets committed, and loads in every future session |

More on how each one is built: [docs/skill-anatomy.md](docs/skill-anatomy.md).

## How we keep it human

Three layers, applied in this order.

1. **Never invent.** No fact, number, name, quote or result goes into an output unless the source or the person gave it. Where a detail is missing, the draft says `[ADD: ...]` and asks. The carousel skill runs a fact audit that fails any slide carrying a number the transcript does not contain.
2. **Ban the tells.** Each skill carries a list of patterns that mark text and design as machine-made, and rewrites them on sight: dashes used as punctuation, "not X, it's Y" contrasts, staged run-ups, recap endings, chatbot sign-offs, filler verbs, template headlines, purple gradients, neon glow, fake UI. The writing list started from three open-source anti-slop projects and has grown from the person's own feedback since.
3. **A second reader who did not write it.** Design work goes to a separate reviewer agent that never edits files. It reads every slide at full size and at arm's-length size, runs a two-second "what did I understand?" test, and returns pass or a fix list. The loop repeats until pass, and stops to ask the human after three failed rounds with no progress.

The full rule set: [docs/quality-gates.md](docs/quality-gates.md).

## How it learns

Corrections do not stay in a chat. When the person says "never do that again" or posts a different version from the draft, a retro step writes the lesson into the one repo file that governs that work (a project rules file, a runbook, a playbook), commits it, and the next session reads it. The writing skill goes further: each lesson bumps its version, gets a changelog line, passes a validator and is pushed, so every machine and cloud session runs the latest rules.

## Progress so far

| When | What shipped |
|---|---|
| Sep 2026 | Retro loop: session learnings written back into repo files, manual trigger |
| 4 Oct 2026 | Writing skill v1.0, compiled from three MIT-licensed anti-slop skills |
| 5 Oct 2026 | Comment reply skill; writing skill learns the person's own style rules |
| 15 to 17 Oct 2026 | Carousel director, independent reviewer agent, 32-design library; the old design-taste rules folded in |
| 23 Oct 2026 | Writing skill reaches its eighth release (v1.1.2) in 19 days, each one driven by real feedback |
| 25 Oct 2026 | Podcast hook skill, built from an evidence study of 18 episodes and a blind verification pass |

Detail and what comes next: [docs/progress.md](docs/progress.md).

## What it changes

- **Volume without slop.** Already tested on 58 carousels made from the content of 3 videos, each one fact-checked against its source, reviewed and in a design its neighbours do not repeat.
- **Feedback is given once.** A correction becomes a rule in a file, so the same mistake does not come back next week or on another machine.
- **Decisions rest on evidence.** The podcast hook rules come from measured episodes with timestamps, so an editor can check every claim instead of trusting taste.
- **The human stays the editor.** Skills draft, check and package. A person approves every export and posts every word.

## Use the pattern

[templates/SKILL.template.md](templates/SKILL.template.md) is a blank skill in the same shape: trigger, read-first list, hard rules, workflow, gates, deliverable, retro. Copy it into your agent's skills folder and fill it in.

## Confidentiality

The client, its people, its channels, its prompts, its data and every output stay in private repositories. Nothing here is derived from them by copy: this repository has its own history, and the documents describe the method in general terms. Numbers are counts and ratios only.

## License

MIT. See [LICENSE](LICENSE).
