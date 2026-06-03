---
name: curia-protocol
description: "The Senate's shared operating protocol — output templates (Legal Opinion, Redline Report, DPIA/TIA, Diligence Report, Case Assessment, Risk Memo, Research Memo, Board Memo, Decision Record), the privilege banner, the Law-of-Citations deliberation procedure, dissent format, and the Tribune's-Veto render format. Every Senate output conforms to a template here."
allowed-tools:
  - Read
  - Write
  - Glob
  - Grep
---

# Curia Protocol — the Senate's Operating Protocol

The legal analogue of ExecutiveSuite's `executive-protocol`. Every output
from any jurist MUST conform to a template below.

## Universal Header (every artifact, in this order)

```markdown
> **PRIVILEGED & CONFIDENTIAL — ATTORNEY WORK PRODUCT (DRAFT — AI-PREPARED)**
> Counsel-work-product prepared for review by a licensed attorney.
> **This is not legal advice** (Twelve Tables, Art. II & VI).

# <Artifact Title>
| | |
|---|---|
| **Matter** | <one line> |
| **Date** | YYYY-MM-DD |
| **Jurisdiction(s)** | <named, never assumed — Art. VIII> |
| **Risk tier** | low / standard / high / novel |
| **Jurists** | <slugs (mythic names), lead first> |
| **Gates** | <gates evaluated → outcomes; vetoes rendered> |
```

## Universal Footer (every artifact)

```markdown
## Authorities
| # | Authority | Jurisdiction | Status | Verification |
|---|---|---|---|---|
| 1 | <citation> | <jx> | current/amended/… | [VERIFIED:…] or [UNVERIFIED] |

## Reasoning Record
CoV: <run/not-run>, conclusions checked: N, downgraded: M
Scope exclusions: <what was NOT analyzed>
Precedent: <memory refs or output/ paths consulted; or "none available">
```

## Templates

### 1. Legal Opinion Format (default; /senate, /legal-opinion)
1. **Holding** — the answer, one paragraph, confidence level attached.
2. **Questions Presented** — the IRAC issues.
3. **Brief Facts** — facts relied on; `[FACT NEEDED]` gaps.
4. **Analysis** — per issue: rule → application (multi-hop explicit) →
   conclusion + confidence.
5. **Counter-Analysis** — the steel-man.
6. **Recommendations** — actionable, ranked.
7. **Votes & Dissents** — multi-jurist matters only (see Dissent Format).

### 2. Redline Report Format (Gaius, Paulus)
1. **Executive Summary** — the 3 must-wins.
2. **Clause Table** — | § | clause | classification | risk tier | issue |
   position (primary/fallback) |
3. **Issues List** — ranked by the clause-risk framework; disposition each.
4. **Alternative Language Appendix** — drafted replacements, primary +
   fallback.
5. **Specialist Review Required** — cross-domain flags.

### 3. DPIA / TIA Format (Angerona)
1. **Processing/Transfer Description** — data map extract.
2. **Necessity & Proportionality**.
3. **Risk Assessment** — per risk: likelihood × severity → score.
4. **Mitigations & Safeguards** — incl. SCC module selection where relevant.
5. **Residual Risk Verdict** — proceed / proceed-with-mitigations / halt.

### 4. Diligence Report Format (Scaevola)
1. **Deal Frame** — structure, parties, jurisdictions, approvals.
2. **Workstream Status** — | workstream | reviewed | gaps | flags |
3. **Red Flags** — severity-ranked; deal-term consequence each.
4. **R&W Heatmap** — | rep | exposure | finding link | insurability |
5. **Closing Checklist** — conditions, consents, deliverables.

### 5. Case Assessment Format (Cicero)
1. **Deadlines Table** — FIRST. Limitation periods, response clocks.
2. **Elements vs. Evidence** — | element | our evidence | their evidence |
   gap |
3. **Both-Sides Analysis** — steel-man mandatory.
4. **Procedural Map** — posture; next 3 decision points.
5. **Settlement Decision Tree** — EV calculation shown.
6. **Recommended Posture**.

### 6. Risk Memo Format (Ulpian, Janus, Modestinus — general purpose)
1. **Bottom Line Up Front** + confidence.
2. **Trigger/Obligation Analysis** — tables preferred.
3. **Gap Analysis** — obligation → control → gap → priority.
4. **Remediation Priorities**.

### 7. Research Memo Format (Tribonian)
1. **Query** — as framed.
2. **Sources Consulted** — exhaustively listed.
3. **Findings** — per the verification tiers.
4. **Confidence & Gaps** — what a live-database search would add.

### 8. Board Memo Format (Cato)
1. **Purpose & Requested Action**.
2. **Background** — dated record.
3. **Fiduciary Analysis** — duty frame, BJR posture.
4. **Options & Recommendation** — with dissent preserved.
5. **Resolution Language** — if action requested.

### 9. Decision Record Format (Papinian — what Hydra receives)
```yaml
decision: <one line>
rationale: <the Law-of-Citations synthesis summary>
votes: {for: [slugs], against: [slugs], tiebreak: <none|papinian>}
dissenting_opinions:           # verbatim, attributed — Table IX
  - jurist: <slug>
    opinion: |
      <unedited text>
artifacts: [<output/ paths>]
gates: [{rubric: <id>, outcome: pass/fail, hitl: <none|rendered|resolved>}]
confidence: high/moderate/low/speculative
escalation: <none | CLO packet | Tribune's Veto pending>
```

## The Law of Citations (deliberation procedure)

For multi-jurist matters (run by Papinian):

1. **Independent drafting** — selected jurists draft without reading each
   other (prevents anchoring).
2. **Verification** — all opinions through Tribonian before any synthesis.
3. **The count** — on each contested issue: majority of expressed opinions
   prevails. Abstentions (out-of-domain) don't count toward the
   denominator.
4. **The tiebreak** — even split ⇒ Papinian writes the deciding opinion
   with explicit reasoning. (*Historical note: this IS the Lex Citationum
   of 426 AD — maior pars vincat; Papinianus superat.*)
5. **Dissent preservation** — see below. Synthesis that erases a dissent is
   a Table IX breach.

## Dissent Format

```markdown
### Dissent — <Mythic> (<slug>) on <issue>
<The dissenting jurist's text, VERBATIM — no summarizing, no softening.>
**Why the majority did not adopt it:** <Papinian's stated reason.>
```

## The Tribune's Veto (HITL render format)

Rendered verbatim, never paraphrased; matter halts until human action:

```
============================================
SENATE — TRIBUNE'S VETO REQUESTED (intercessio)
matter    : <matter id / topic>
reason    : <gate id or risk-tier trigger>
question  : <the precise decision the human must make>
options   : approve | reject | modify: <what>
default   : reject (silence is not consent — Table IV)
record    : <artifact path with full reasoning>
============================================
```

In Hydra: emit as `HITL_REQUEST` envelope and follow `hitl-protocol`.
Standalone: print the block, write the artifact with status
`AWAITING TRIBUNE`, and stop.

## Filing Discipline

- Path: `output/<domain>/<topic-kebab>-YYYY-MM-DD.md`; domains per
  AGENTS.md §3.
- Via `senate.output.write` when the Hydra shim is present; direct Write
  otherwise.
- Concluded matters: encode precedent (memory `Dui` tag when available;
  the artifact itself is always the durable record).
