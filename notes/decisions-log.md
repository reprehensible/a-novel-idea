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

### 2026-07-31 — Project architecture
- Chose external story-bible system over keeping manuscript in context:
  at 250–300k words (~400k tokens) the manuscript cannot fit in a context
  window, so repository files are the memory system from day one.
- Compression strategy: per-chapter summaries (~200 words each) + current-state
  continuity file + promises ledger. A drafting session reads those in full
  plus only the last 1–2 chapters of actual prose.
