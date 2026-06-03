# Senate ↔ ExecutiveSuite — The Complementarity Contract

ExecutiveSuite already has two legal-adjacent executives. The Senate
**complements** them; it never duplicates or supersedes them. This file is
the boundary treaty.

## The three seats

| Seat | System | Owns | Does NOT own |
|---|---|---|---|
| **CLO** (`clo`, Themis in Hydra's executive crown) | ExecutiveSuite | Strategic legal judgment: go/no-go on material legal exposure, board/shareholder counsel of record, litigation *strategy* authority, M&A legal leadership | Operational depth (delegates down) |
| **CCO** (`chief-compliance-officer`) | ExecutiveSuite | Compliance *program*: mandates controls, training, remediation timelines; three-lines-of-defense second line | Legal positions (CLO's), obligation mapping depth (Senate supplies) |
| **The Curia** (12 jurists) | Senate | The operating legal department: drafting, redlines, DPIAs/TIAs, obligation catalogs, diligence, clearance, case assessment, citation verification | The enterprise go/no-go (CLO's), control mandates (CCO's), business strategy (CEO's) |

**One line**: the Senate prepares; the CLO judges; the CCO mandates.

## Handoffs

**Upward (Senate → CLO)** — the *CLO escalation packet*: triggered by
Papinian's materiality thresholds (risk tier ≥ high with enterprise
consequence, settlement/deal commitments, board-facing exposure).
Contents: the DECISION_RECORD + dissents + a one-page recommendation
framed for go/no-go. Format: Executive Memo-compatible (the CLO's world
runs on `executive-protocol`).

**Upward (Senate → CCO)** — control-mapping handoffs: Ulpian's
obligation→control→gap registers, ready for the CCO to mandate
remediation. The Senate maps; the CCO orders.

**Downward (CLO/CCO → Senate)** — via Hydra `C_SUITE_DECISION_PACKET`
envelopes or direct command invocation: "deep-dive this exposure",
"catalog obligations for regime X", "diligence this target".

**Peer surfaces** — `mna-cockpit` (deal strategy; Scaevola supplies the
legal workstreams), `crisis-warroom` (crisis matters; Cicero supplies
dispute posture), `caio` (AI governance; Ulpian's AI-Act classifications
and Cato's board AI reporting feed it), `cfo` (litigation reserves,
indemnity economics).

## Name discipline

**Themis belongs to the CLO** (Hydra executive crown heads.yaml). The
Senate deliberately uses Roman jurists (Papinian, Ulpian, Gaius, Paulus,
Modestinus, Scaevola, Tribonian, Cicero, Cato) and Roman deities
(Angerona, Minerva, Janus) — no collisions, and a clean mythological
seam: the Greek goddess of divine order sits above; the Roman jurists who
operationalized law sit below. Themis says *what must be*; the Curia
writes *how it shall be done*.
