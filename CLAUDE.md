# A Novel Idea — Project Charter

This repository is a novel-writing project. The goal is a complete, coherent,
publishable-quality novel of **250,000–300,000 words**, written by Claude in
collaboration with the author (Bruce), who provides high-level direction.

This file defines how the project works. Read it at the start of every session.

## The core problem this repo solves

The finished manuscript will be ~400k tokens — it can never fit in a context
window. Therefore **the repository, not the context window, is the memory.**
Every fact needed to write chapter N must be recoverable from the story bible
and tracking files without re-reading the manuscript. If a fact matters and it
only exists in prose, it is effectively lost. The iron rule:

> **A drafting session must be fully bootstrappable from STATUS.md + the bible
> + the tracking notes + the last 1–2 chapters of prose.**

## Repository layout

```
CLAUDE.md                    This charter. Workflow + rules.
STYLE.md                     Prose style guide. Read before every drafting session.
STATUS.md                    Living dashboard: current phase, word count, what's next.
bible/
  setting.md                 World, history, factions, technology/magic systems, locations.
  characters/                One file per significant character (goals, voice, secrets, arc).
  plot/
    outline.md               Full novel outline: acts → chapters → scene beats.
    promises.md              Setup/payoff ledger (Chekhov's guns, mysteries, foreshadowing).
  timeline.md                In-world chronology of events, past and present.
  glossary.md                Canonical spelling of every invented term and name.
manuscript/
  ch001-title.md ...         One file per chapter. Prose only, no notes.
notes/
  chapter-summaries.md       150–250 word summary of every drafted chapter. The compressed novel.
  continuity.md              Character/world state snapshots: who knows what, injuries, items, locations.
  decisions-log.md           Dated log of authorial decisions, changes of direction, retcons.
```

## Phases

1. **Phase 0 — Setup** (this commit): scaffold in place, awaiting story prompt.
2. **Phase 1 — Development**: from the author's 1–2 paragraph prompt, build the
   full bible: setting, magic/tech systems, character roster, complete outline
   with per-chapter beats, timeline. Get author sign-off before drafting.
3. **Phase 2 — Drafting**: write chapters in order, following the session
   protocol below. Update tracking files after *every* chapter.
4. **Phase 3 — Revision**: continuity audit against the tracking files, prose
   pass for crutch words and pacing, then author review.

Phases can overlap (the outline may get revised mid-draft), but every deviation
from the outline gets recorded in `notes/decisions-log.md` and propagated to
the outline itself. The outline is always kept true to the current plan, not
the original plan.

## Drafting session protocol

**Before writing a chapter:**
1. Read `STATUS.md` — confirms where we are and what's next.
2. Read `STYLE.md`.
3. Read the outline beats for the target chapter, plus the beats for the 2–3
   chapters on either side (so the chapter aims where it must land).
4. Read `notes/chapter-summaries.md` in full (it stays compressed precisely so
   this is always affordable).
5. Read the `notes/continuity.md` entries for every character appearing in the
   chapter, and any relevant `bible/` files (POV character file always).
6. Read the **full prose** of the previous 1–2 chapters, for voice and flow.

**After writing a chapter — never skip, never batch more than one chapter:**
1. Add its summary to `notes/chapter-summaries.md`.
2. Update `notes/continuity.md` for every character whose state changed.
3. Update `bible/plot/promises.md`: new setups planted, payoffs delivered.
4. Update `bible/timeline.md` and `bible/glossary.md` if anything new appeared.
5. Update `STATUS.md` (word counts, next chapter).
6. If the chapter deviated from the outline, update the outline and log it in
   `notes/decisions-log.md`.
7. Commit with message `ch NNN: <chapter title> (~N,NNN words)`.

The post-chapter bookkeeping is not optional overhead — it *is* the memory
system. A chapter is not "done" until its bookkeeping is committed.

## Canon and consistency rules

- **The bible is canon.** If prose and bible conflict, that's a bug: fix one,
  log it in `decisions-log.md`.
- **Invented terms** get a `glossary.md` entry the first time they appear.
  Never trust memory for spelling of invented names — check the glossary.
- **Speculative systems are hard-edged.** Rules for any magic/tech system are
  written in `bible/setting.md` *before* the system is used to resolve a plot
  problem. No capability appears in a climax that wasn't established earlier —
  track this in `promises.md`.
- **Knowledge states matter.** `continuity.md` tracks who knows what. Before a
  character acts on information, verify they have it.
- **Dates and travel times** must be consistent with `timeline.md`.

## Scale plan

- Target: 250k–300k words ≈ **70–80 chapters at 3,000–4,500 words** each,
  plus possible shorter interludes.
- Structure: likely 4–5 parts/acts. Exact structure decided in Phase 1.
- Write chapters **one at a time**, in order. Resist compressing scenes to
  move faster — pacing failure through scene compression is the primary
  known failure mode; see STYLE.md.

## Author interaction

- The author sets direction at a high level; Claude fleshes out everything and
  keeps it consistent. When a genuinely story-defining fork arises (killing a
  major character not in the outline, changing the ending), surface it to the
  author. Everything else: decide, log the decision, keep writing.
- Author feedback on any chapter overrides the outline; propagate the change.
