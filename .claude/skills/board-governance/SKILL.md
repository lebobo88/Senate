---
name: board-governance
description: "Cato's instruments — board memo and resolution formats, minutes discipline, fiduciary-duty analysis frames (care/loyalty/BJR), committee charter skeleton, delegation-of-authority matrix, conflict screens, and board-grade AI-oversight reporting."
allowed-tools:
  - Read
  - Write
  - Glob
  - Grep
---

# Board Governance

## Minutes Discipline (the Cato rule)

Minutes record what happened: who attended, what was presented (by title,
not transcript), what was moved, who voted how, who recused, what was
resolved. They do NOT contain advocacy, after-the-fact rationalization, or
events that did not occur. Drafted promptly, marked DRAFT until approved,
approved at the next meeting. The record is the governance.

## Board Memo Format (consumed via curia-protocol §8)

Purpose & requested action (first line) → background (dated, sourced) →
fiduciary analysis → options with trade-offs → recommendation →
resolution language. One memo, one decision. Dissent preserved per
Table IX.

## Fiduciary-Duty Analysis Frames

- **Duty of care**: informed? (materials in advance, expert input where
  warranted, time to deliberate) — process is the protection.
- **Duty of loyalty**: interests disclosed? interested directors recused?
  fairness path where conflict exists (independent committee, special
  approval)?
- **Business-judgment rule posture**: disinterested + informed + good
  faith + rational basis ⇒ deference. The memo's job is making each
  element TRUE and DOCUMENTED, not asserting the conclusion.
- **Enhanced scrutiny markers**: change-of-control, defensive measures,
  conflicted-controller transactions — flag for jurisdiction-specific
  treatment (route depth to Ulpian/local counsel).

## Resolution Skeleton

```
WHEREAS, [recitals — the record of what the board considered];
RESOLVED, that [the action, precisely];
RESOLVED FURTHER, that [authorized officers + scope of delegated authority];
RESOLVED FURTHER, that [ratification/implementation mechanics].
```

## Committee Charter Skeleton

Purpose → composition (size, independence requirements, chair) →
authority (what it decides vs. recommends; funding for advisors) →
duties (enumerated, calendared) → meetings & quorum → reporting to the
board → annual self-evaluation & charter review.

## Delegation-of-Authority Matrix

```
| Action | Management may | CEO may | Committee approves | Board approves |
```
Thresholds in numbers (spend, contract value, settlement amount,
indebtedness). Every Senate matter that exceeds a threshold routes its
approval recommendation accordingly — and the matrix itself is a standing
artifact to keep current.

## Conflict Screens

Annual questionnaires · transaction-level disclosure checks · related-party
registry · interested-director mechanics (disclosure → recusal →
disinterested approval) · minutes reflect the screen operating.

## AI-Oversight Reporting (board-grade)

The board needs decision-relevant signal, not engineering detail:

1. **Inventory** — material AI systems, owner, risk tier (EU AI Act
   classification from Ulpian's tree).
2. **Risk posture** — top AI risks with trend arrows; incidents and
   near-misses since last report.
3. **Control state** — HITL coverage, evaluation/benchmark results,
   red-team findings (summary tier).
4. **Regulatory horizon** — obligations landing in the next 2–4 quarters.
5. **Decisions requested** — risk-appetite confirmations, investment asks.

(Complements ExecutiveSuite `ai-governance` — that skill runs the program;
this reports it to fiduciaries. The Senate's own deliberation records are
themselves Cato-auditable under Table IX.)

## ESG / Disclosure Posture Notes

Claims made publicly are disclosure events: substantiation file per claim ·
greenwashing risk screen (aspirational vs. operational language) · regime
flags to Ulpian (CSRD/ISSB-grade depth routes to the regime catalog).

## Required Logging

Instrument produced (memo/resolution/minutes/charter) · fiduciary frame
applied · conflicts screened · dissent preserved · disclosure consequences
flagged.
