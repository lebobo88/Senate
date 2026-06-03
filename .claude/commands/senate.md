---
description: "Full Curia deliberation — Papinian triages the matter, convenes the bench, runs the Law of Citations, and files one auditable DECISION_RECORD. The Hydra claude-skill entrypoint for the legal-compliance squad."
argument-hint: "<legal matter in free text, or a Hydra envelope JSON>"
---

# /senate — Convene the Curia

Run the matter in `$ARGUMENTS` through the full five-movement Curia
workflow (AGENTS.md §2), led by the **general-counsel** agent (Papinian).

## Procedure

0. **Constitution check** — read `CONSTITUTION.md`. If missing, halt:
   "The Curia does not deliberate without the Twelve Tables."

1. **Intake (Papinian)** — invoke the `general-counsel` agent as crew lead.
   - Free text ⇒ frame the matter; envelope JSON (`HANDOFF`,
     `C_SUITE_DECISION_PACKET`, `PRD`, `CREATIVE_BRIEF`) ⇒ validate,
     preserve `parent_id`, extract constraints.
   - Redact personal data not needed for the matter (Table X).

2. **Recall** — query precedent (eights-memory domain `legal`, scope
   `team:senate` when available; else scan `output/`). Note absence
   explicitly.

3. **Triage & convene** — apply Papinian's risk-tier framework; announce
   bench + tier. Engage consilium (Paulus/Modestinus/Janus) only through
   their parent jurists.

4. **Opinions in parallel** — task each selected jurist (its agent file)
   with its slice. Jurists draft independently — no cross-reads.

5. **Verification (Tribonian)** — invoke `citation-verifier` on every
   opinion. Fabricated authority ⇒ breach protocol (kill, log, veto).

6. **The Law of Citations (Papinian)** — majority per contested issue;
   even split ⇒ Papinian's reasoned tiebreak; dissents preserved verbatim
   (`curia-protocol` Dissent Format).

7. **Gates** — evaluate applicable rubrics (`.claude/rubrics/`):
   citation-integrity@1 and aba-512-ethics@1 always; privacy/AI-Act/OSS/
   compliance gates as in scope. Any `hitl_required` failure or high/novel
   tier ⇒ render the **Tribune's Veto** verbatim and HALT (emit
   `HITL_REQUEST` in Hydra; print block + `AWAITING TRIBUNE` standalone).

8. **File** — write the Decision Record (`curia-protocol` §9 embedded in a
   Legal Opinion artifact) to `output/legal/<topic>-<date>.md` (via
   `senate.output.write` when the Hydra shim is present). Encode precedent
   (Dui tag when memory available). In Hydra: return the
   `DECISION_RECORD` envelope.

## Output contract

One artifact, carrying: privilege banner · Article VI notice · matter
header · holding + analysis · votes & dissents · gate outcomes ·
authorities table (verified/unverified) · reasoning record.

## Examples

```
/senate Review this SaaS MSA for our EU rollout — data processing terms attached
/senate {"type":"HANDOFF","payload":{...}}
/senate Assess whether our new recommendation engine is high-risk under the EU AI Act
```
