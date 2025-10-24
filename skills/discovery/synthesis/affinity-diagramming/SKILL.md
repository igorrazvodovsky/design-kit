---
name: Affinity diagramming
description: Derives stable, prioritized themes from many notes by producing several independent clusterings under different lenses (perspectives, temperatures, seeds), then merging them with agreement scoring.
---

## When to use
- You have dozens–hundreds of research notes or insight cards.
- You want defensible themes without human co-clusterers.

## Inputs
A flat list of notes/insights (one idea per item).

## Instructions
1) **Normalise inputs.** Ensure each note is ≤1–2 sentences and tagged with a source ID.
2) **Define lenses.** Prepare 4–6 prompts that force different perspectives, e.g.:
   - Customer Outcome, Business Value, Technical Feasibility, Operational Risk,
   - Emotional/Jobs-to-be-Done, Temporal Phase (before/during/after).
3) **Generate independent clusterings.** For each lens:
   - Sample once with mild randomness (e.g., varied wording/seed/temperature).
   - Produce: (a) cluster labels with 2–3 sentence definitions, (b) membership lists of note IDs.
4) **Compute agreement.** For every pair of clusters across lens runs, compute overlap (e.g., Jaccard on note IDs). Merge clusters whose overlap ≥0.5; keep alternates if 0.3–0.5 reveals a meaningful sub-theme.
5) **Name merged themes.** Create a single label and 2–3 sentence definition that cover the merged set. Keep provenance: list the top contributing notes and which lenses supported the theme.
6) **Score & rank.** For each theme, compute:
   - **Support** = #notes
   - **Consensus** = #lenses that independently produced a matching cluster
   - **Signal** = average note “specificity” (short, concrete, non-duplicative)
   Rank by (Consensus first, then Support), and break ties with Signal.
7) **Output.** Return:
   - Final theme list (label, 2–3 sentence definition, top 5 exemplar notes with IDs),
   - A matrix showing lens × theme consensus,
   - An “alternates” appendix (sub-themes that didn’t meet the merge threshold).

## Quality checks
- Any theme is traceable to its notes (IDs) and at least 2 lenses (unless clearly niche).
- Definitions avoid solution language; they describe patterns in the data.

## Failure modes & mitigations
- **One giant bucket** → raise merge threshold; add a contradictory lens (e.g., “anti-patterns”).
- **No consensus** → lower threshold slightly or increase the number of lenses.
- **Duplicate themes** → prefer the label with the clearest definition and strongest consensus; demote the duplicate to “alternate.”

