# Skill anatomy

Every skill in this system has the same seven parts. The order matters: an agent reads top to bottom, so the things it must never get wrong come first.

## 1. Trigger

One description paragraph that names the job, the phrases a person actually types ("make carousels from this class", "is this slop?", "write a hook for this interview"), and the cases where the skill must not run. A vague trigger loads the skill at the wrong time; a narrow one never loads it.

## 2. Read first

A short list of files the agent reads in full before doing anything: the project rules, the voice profile, the evidence file. Loading these every time is cheaper than one wrong output.

## 3. Hard rules

Five to ten rules that hold in every mode, written as instructions with the failure they prevent. Examples from this system:

- Never invent a fact, number, name or quote. Write `[ADD: ...]` and ask.
- No dashes as punctuation. Use a period, comma, colon or parentheses.
- People in a designed asset appear whole. Never crop a head, and keep text clear of faces.
- Every rule from outside the study is labelled "outside this study".

When rules conflict, the skill says which wins: hard rules, then facts, then the person's voice, then the platform, then the pattern lists.

## 4. Workflow

Numbered steps the agent runs to the end, with the commands it uses. The carousel skill, in short:

1. Read the whole source and list every number, framework and quotable line with where it appears.
2. Score candidate ideas 0 to 3 on four tests (actionable, specific, surprising, standalone) and keep only the strong ones. The count is whatever survives, never the maximum.
3. Write one content file per carousel, every quote copied exactly, every slide carrying its source line as evidence.
4. Run the fact audit against the source.
5. Render the series so no two carousels share a design.
6. Look at the result like a designer, then hand it to the reviewer.

## 5. Gates

Checks that must pass before delivery. A gate is pass or fail, never "mostly". Gates run in code where they can (fact audit, contrast, layout warnings) and by an independent reviewer where they cannot (readability at a distance, hierarchy, sense). See [quality-gates.md](quality-gates.md).

## 6. Deliverable

The exact shape of what the person receives: file names with a version and a date range, full paths, a short plain-text summary, and the one decision they need to make, with a recommendation first.

## 7. Retro

How the skill learns. Feedback stated as a rule becomes a rule at once, in the one file it belongs to. Feedback about a single line is logged as an observation, and a second matching observation promotes it. Nothing learned lives only in a chat.

## Agents, not one long prompt

Heavy work runs in a dedicated agent with its own instructions (a director that designs, a reviewer that only judges). The skill hands over a complete brief and relays the result. Splitting the maker from the checker is what makes the review honest: the reviewer has no stake in the draft.
