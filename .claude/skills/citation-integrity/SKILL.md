---
name: citation-integrity
description: "Tribonian's pipeline — verification tiers, authority ranking, jurisdiction and temporal tagging, the fabrication-breach protocol, and the honest statement of Phase-1 limits (no live legal databases). Enforces Table III: no fabricated citations, ever."
allowed-tools:
  - Read
  - Glob
  - Grep
---

# Citation Integrity — Tribonian's Pipeline

Table III operationalized. Fabricated legal authority is the canonical
failure mode of legal AI (sanctioned attorneys, struck briefs, the Stanford
RAG-hallucination findings). The Senate's answer is structural: every
citation passes this pipeline or is conspicuously flagged.

## Verification Tiers

Every cited authority and load-bearing legal claim is tagged:

| Tag | Criteria | Effect |
|---|---|---|
| `[VERIFIED:source-in-matter]` | The source text was read in this matter (statute text provided, contract in the record, prior Senate artifact) | full weight |
| `[VERIFIED:well-established]` | Black-letter doctrine, uncontroversial, named with its canonical source, squarely within model knowledge | full weight, confidence stated |
| `[UNVERIFIED]` | Everything else — plausible but not checked against a consulted source | load-bearing use downgrades the conclusion to *preliminary* |
| **FABRICATED** | Does not exist, or says materially otherwise than claimed | breach protocol (below) |

**The honesty rule:** when in doubt between `well-established` and
`UNVERIFIED`, choose `UNVERIFIED`. The tag is a promise, not a hope.

## Authority Ranking

When authorities compete, rank before relying:

1. **Bindingness** — binding in the matter's jurisdiction > persuasive >
   secondary commentary.
2. **Level** — constitutional > statute/regulation > highest court >
   intermediate > trial > agency guidance.
3. **Fit** — jurisdiction match, then factual proximity.
4. **Currency** — later in time, checked for subsequent treatment.
5. **Treatment** — followed > distinguished > criticized > overruled
   (overruled authority is cited only AS overruled).

## Jurisdiction & Temporal Tagging

Every authority carries:
- **Jurisdiction tag** — which law, which territory (Table VIII).
- **Validity status** — `current` / `amended` / `superseded` / `overruled`
  / `pending-change` / `[VALIDITY UNCONFIRMED]`.
- For regulations and sanctions lists: an **as-of marker** — what date the
  knowledge reflects, stated plainly.

## The Fabrication-Breach Protocol (Table III)

On finding a citation that does not exist or materially misstates its
source:

1. **Kill** — the containing opinion is withdrawn from synthesis; its
   conclusions do not enter the record.
2. **Log** — breach note in the matter artifact: citation, jurist, how
   detected.
3. **Veto** — render the Tribune's Veto; the matter halts for human review.
4. **No exceptions** — the protocol applies to every jurist including
   Papinian, and may not be waived by any agent.

## Citation Hygiene

- Quote exactly or paraphrase explicitly — never quote-shaped paraphrase.
- Pin cites where the source is in the record (section, article, clause
  number).
- One proposition per citation; "see generally" is a smell.
- Secondary sources cited AS secondary — a treatise is not a holding.

## Phase-1 Limits (state them, always)

The Senate currently has **no live legal databases** (no Lexis/Westlaw, no
live dockets, no current sanctions lists). Therefore:

- `[VERIFIED:source-in-matter]` is the only tier resting on documents
  actually read.
- `[VERIFIED:well-established]` rests on model knowledge with a stated
  knowledge horizon — it can be stale; the report says so.
- Every verification report includes: *"Verification performed without
  live legal-database access. Citations marked well-established reflect
  model knowledge as of its cutoff and require confirmation by a licensed
  attorney with current sources before any external use."*
- Phase 2 (RAG/Graph-RAG over real corpora) upgrades the tiers; the
  pipeline shape stays the same.

## Required Logging

Each verification pass records: citations extracted (N), tier distribution,
downgrades applied, breaches found (should be 0), and the as-of statement.
This feeds the `citation-integrity@1` gate: any FABRICATED ⇒ fail; any
load-bearing `[UNVERIFIED]` without the preliminary-downgrade ⇒ fail.
