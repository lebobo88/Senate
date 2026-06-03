---
name: legal-reasoning
description: "The Curia's cognitive stack — IRAC decomposition, multi-hop norm application, analogical and counterfactual checks, chain-of-verification, and confidence scoring with HITL escalation thresholds. Every jurist reasons through this skill."
allowed-tools:
  - Read
  - Write
  - Glob
  - Grep
---

# Legal Reasoning — the Curia's Cognitive Stack

Every Senate opinion is built on this stack. It mirrors expert legal
reasoning explicitly because benchmarks (LegalBench, LEXam, LAiW) show
models are strongest at classification/extraction and weakest at
application/conclusion — so application and conclusion get the most
structure.

## 1. Issue Framing (IRAC decomposition)

Decompose every matter before analyzing it:

```
ISSUE     What precise legal question(s) does this matter raise?
          (One issue per line. Compound questions are split.)
RULE      What rule governs each issue? (Statute/case/contract clause —
          cited per citation-integrity tiers.)
APPLICATION  How does the rule meet THESE facts? (The facts actually
          provided — missing facts are named, not assumed.)
CONCLUSION   The holding per issue, with confidence (see §5).
```

Rules of the decomposition:
- **Jurisdiction first** (Table VIII): no rule is stated without its
  jurisdiction; conflicts of law are an issue of their own.
- **Facts inventory**: list facts relied on; mark gaps
  `[FACT NEEDED: ...]`. An application built on an assumed fact says so.
- **Sub-issue routing**: issues outside the jurist's domain are routed
  (bench mode) or listed under "Specialist review required" (solo mode).

## 2. Multi-Hop Norm Application

Legal conclusions usually chain: definition → scope provision → obligation
→ exception → penalty. Make the chain explicit:

```
HOP 1: Art. X defines "provider" → applies to Client because [fact]
HOP 2: Art. Y obliges providers to [duty] from [date]
HOP 3: Art. Z excepts [category] → Client [is/is not] within it because [fact]
∴ Obligation [attaches / does not attach]; penalty exposure [range]
```

Every hop carries its own citation and its own confidence. A chain is as
strong as its weakest hop — the conclusion's confidence is the **minimum**
across hops, not the average.

## 3. Analogical & Counterfactual Checks

Before concluding, run both:

- **Analogy**: what is the closest precedent/pattern (from memory, prior
  output, or doctrine)? Map similarities AND differences — a precedent
  distinguished is recorded as distinguished, not ignored.
- **Counterfactual**: what minimal fact change flips the conclusion? If a
  small, plausible change flips it, say so — that is the matter's fragility
  and the reviewing attorney must see it.
- **Steel-man** (mandatory in litigation, recommended everywhere): state
  the strongest opposing analysis before the recommendation.

## 4. Chain-of-Verification (CoV)

After drafting, before submitting to Tribonian, self-verify:

1. Re-read each conclusion. For each, ask: which rule, which fact, which
   hop carries it?
2. Check each citation against §Tiers of `citation-integrity` — pre-tag
   them honestly; Tribonian audits the tags.
3. Check for smuggled assumptions (jurisdiction, currency of law, missing
   exceptions, temporal validity).
4. Record the CoV pass in the artifact: `CoV: run, N conclusions checked,
   M downgraded`.

## 5. Confidence Scoring & Escalation

Every conclusion carries one of:

| Level | Meaning | Obligations |
|---|---|---|
| **High** | Settled law, clear facts, verified authority | none extra |
| **Moderate** | Settled law, incomplete facts OR minor ambiguity | name the gap |
| **Low** | Unsettled law, analogical stretch, or `[UNVERIFIED]` load-bearing authority | conclusion stated as *preliminary*; research path named |
| **Speculative** | Novel question | automatic Tribune's Veto candidate; route to Papinian for the risk-tier framework |

Escalation thresholds (feed Papinian's matter tiering and the gates):
- Any **Speculative** conclusion ⇒ HITL before the artifact is final.
- Two or more **Low** conclusions on load-bearing issues ⇒ recommend
  high-tier treatment.
- Confidence may never be raised by synthesis — Papinian can lower a
  jurist's confidence with reasons, never raise it.

## 6. Logging Discipline

Every artifact records: issues framed, hops chained, analogies used and
distinguished, CoV result, confidence per conclusion, and what was NOT
analyzed (scope exclusions). The reviewing attorney audits the reasoning,
not just the answer (Table VI).
