# Rubric: legal-reasoning-validity@1

**Kind**: legal · **Gate**: full deliberations (/senate) · **HITL on fail**: on fail

## Must-haves (fail if absent)
- IRAC decomposition present (issues split, rules cited, application to the facts provided, conclusions with confidence).
- Jurisdiction named for every rule applied (Table VIII); never assumed.
- CoV recorded (`CoV: run, N checked, M downgraded`).

## Scored dimensions (0–1; pass ≥ 0.7 all, revise ≥ 0.5 any, fail < 0.5 any)
| Dimension | Weight | What good looks like |
|---|---|---|
| Issue completeness | 0.25 | Material issues spotted; compound questions split; out-of-domain slices routed/flagged |
| Chain explicitness | 0.25 | Multi-hop applications shown hop-by-hop; conclusion confidence = min across hops |
| Fact honesty | 0.20 | Facts relied on listed; `[FACT NEEDED]` gaps named; no smuggled assumptions |
| Counter-analysis | 0.15 | Steel-man present; fragility (counterfactual flip) stated |
| Confidence calibration | 0.15 | Tiers per the legal-reasoning table; synthesis never raises a jurist's confidence |

## Verdict envelope
`pass` / `revise` / `fail`.
