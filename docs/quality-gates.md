# Quality gates

These are the checks that stand between an AI draft and a published post. They are a summary; the working lists inside each skill are longer and grow with feedback.

## Why AI text sounds like AI

A language model writes the most likely next words, so by default it makes the choice that fits the widest range of readers. A person writes for one reader and one topic, so human choices are uneven and specific. Every tell below is a form of that default. Word habits change with each model release; sentence shapes persist, so the gates hunt shapes first.

## Writing gates

Hard rules (any one fails the draft):

- No invented facts, numbers, names, quotes or results.
- No em or en dashes, and no double hyphens.
- No "not X, it's Y" contrasts, in any language or shape.
- No chatbot residue ("Great question", "I hope this helps").
- No recap endings. End on the last concrete point, a next step or one real question.
- Paste-ready plain text: no markdown in anything the person will post.

Tells that get rewritten on sight:

- One-line dramatic closers and fake-profound kickers.
- Staged run-ups ("Here's the thing", "Honestly?") and faux-insight setups ("What nobody tells you").
- Self-answered questions ("The result? 3x views.").
- Telling the reader what to think ("This distinction matters.").
- Cut-on-sight words: delve, tapestry, testament, seamless, elevate, unlock, game changer.
- Rhythm by rule: triads, matching sentence shapes, fragments everywhere.

A one-off tell proves little. Several together are the evidence, so each draft gets a score out of 50 before and after editing.

## Design gates

- Every number and quote on a slide traces to the source; a code audit fails any that do not.
- No template headlines ("5 things you need to know"). Read each one as a stranger scrolling and rewrite it in the topic's own words.
- No neon glow, gradient headline text, purple-blue gradients, pure black, fake UI, decorative status dots or emoji.
- Body text at least 7:1 contrast against its actual background; headlines at least 4.5:1.
- One dominant element per slide and an obvious eye path.
- House fonts only.
- People appear whole, faces stay clear of text.

## Review gates

- **Far view:** every slide is read again at about 300 pixels wide, roughly a phone at arm's length. What cannot be read there fails.
- **Rush test:** two seconds on the cover, one second per slide, then one line on what was understood. If that line is not the point, the carousel fails.
- **Independent reviewer:** a separate agent that never edits files returns pass or a specific fix list (which element, which colour, which words to cut).
- **Stop rule:** after three failed rounds with no new progress, stop and show the human the open items instead of looping.
- **Human approval:** nothing is exported or posted until a person approves the review sheets.

## Evidence gates (research-led skills)

- Every rule cites a measured example and a timestamp, or is labelled "outside this study".
- A blind re-check of a sample of the coding runs before the rules are trusted. Fields that agree poorly are marked directional, never exact.
- Small samples are called small. A median from six videos is a lead, not a law.

## Sources

The writing gates started from three MIT-licensed projects: [humanizer](https://github.com/blader/humanizer) by Siqi Chen (built on Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)), [stop-slop](https://github.com/hardikpandya/stop-slop) by Hardik Pandya and [no-ai-slop](https://github.com/petergyang/no-ai-slop) by Peter Yang. The compiled skill, with its notices, is public at [svx2027/sv-writing](https://github.com/svx2027/sv-writing).
