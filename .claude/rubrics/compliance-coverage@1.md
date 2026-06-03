# Rubric: compliance-coverage@1

**Kind**: regulatory · **Gate**: regulatory matters · **HITL on fail**: yes

## Must-haves (fail if absent)
- Regime list with applicability reasoning (why each applies / why near-miss regimes don't).
- Obligation → control mapping uses only controls that exist (`GAP` / `[CONTROL UNKNOWN — verify]` for the rest — no invented controls).
- Gap register scored and prioritized (remediate-now / quarter-plan / backlog).

## Scored dimensions (0–1; pass ≥ 0.7 all, revise ≥ 0.5 any, fail < 0.5 any)
| Dimension | Weight | What good looks like |
|---|---|---|
| Regime completeness | 0.30 | Applicable regimes across all named jurisdictions and activities; sectoral overlays caught |
| Catalog depth | 0.25 | Article-level obligations with addressee, trigger, deadline, penalty |
| Mapping honesty | 0.25 | The Ulpian rule observed; gap ratio reported, not hidden |
| Horizon awareness | 0.20 | Pending changes and re-assessment triggers stated (or `[HORIZON UNSCANNED]`) |

## Verdict envelope
`pass` / `revise` / `fail` (+ Tribune's Veto rendered).
