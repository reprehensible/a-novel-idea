# Decisions Log

> Dated, append-only record of authorial decisions: direction changes,
> retcons, outline deviations, style rulings, and the reasoning. This prevents
> re-litigating settled questions and explains why the outline changed.
> When a retcon touches already-drafted prose, note which chapters need fixing
> and track until fixed.

## Prose ban-list additions

(Crutch words/phrases noticed during drafting — supplements the list in
STYLE.md. Check before/after each chapter.)

- *(none yet)*

## Decisions

### 2026-07-31 — Author sign-off; edit-pass mandate
- Author reviewed the development package and directed drafting to begin —
  treated as sign-off on all flagged Phase 1 decisions (none vetoed).
- **New standing guidance from the author:** after drafting each chapter,
  a mandatory edit pass for (1) writing quality — metaphors consistent and
  meaningful, no stock phrasing — and (2) "AI smell" — typically-AI
  constructions; sustain varied scene types and tones without repetition
  or loss of coherence. Implemented as STYLE.md "The edit pass" section +
  step 0 of the post-chapter protocol in CLAUDE.md.

### 2026-07-31 — Phase 1 development decisions (flagged for author sign-off)

Design calls made while expanding the premise; all changeable cheaply now,
expensively later:

1. **Magic system ("the Ken").** Understanding-as-magic with warmth as cost,
   letters (rote) → personal kennings → graving (self-modification, the
   Three Trues). The exponential curve and death-by-misunderstanding are
   implemented via graving's consistency web. "Kenning/kenner/letters"
   vocabulary chosen for the literacy/magic double meaning.
2. **The golden age's tyranny = the Tuning**: industrialized mind-conformity
   (consonance) as the workaround to magic's individuality limit — the
   oppression grows from the magic system rather than beside it.
3. **"The Discord"** as the rebellion's name (myth compresses a plural
   movement into a singular devil). Musical vocabulary family:
   consonance/discord/choir/the Diapason ("the Last Bell"). Author veto
   welcome if the word feels off.
4. **Weapon = prison**: the Diapason maintains Ancarel's seals, so denying
   the weapon necessarily breaks the seals — the heroes *choose* the
   unsealing with eyes open (ch 60, 66). This is the book's thesis-decision.
5. **Serel dies (ch 69)** — pressing to the wick; the mentor-price of the
   climax. Explicitly flagged: killing a major character requires outline
   sign-off, which this document requests.
6. **The Lector survives, tuned** — taken as the woken Archon's instrument
   (irony: the tuner tuned); sequel villain-adjacent thread.
7. **Sarich stands down, unresolved** — walks into the vault deeps; sequel
   thread rather than a death.
8. **Romance:** Joss/Renna slow burn, understated, settled-fact by Part V.
9. **POV roster:** Joss ~60%, Cael ~20%, Serel ~10%, Renna ×2 specials,
   4 epistolary interludes. No additional POVs without a logged decision.
10. **Casualty list (majors):** Wystan (ch 7), Mott (ch 21), Caul (ch 39),
    Serel (ch 69). Tovan maimed, survives. Family survives displaced.
11. **Working title:** *The Warden's Latch*.
12. **Outline granularity:** Parts IV–V beats kept one pass coarser;
    each part gets a beat-tightening pass as drafting approaches it.

### 2026-07-31 — Project architecture
- Chose external story-bible system over keeping manuscript in context:
  at 250–300k words (~400k tokens) the manuscript cannot fit in a context
  window, so repository files are the memory system from day one.
- Compression strategy: per-chapter summaries (~200 words each) + current-state
  continuity file + promises ledger. A drafting session reads those in full
  plus only the last 1–2 chapters of actual prose.
