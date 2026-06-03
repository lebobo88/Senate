# Rubric: eu-ai-act-classification@1

**Kind**: ai-regulatory · **Gate**: matters with an AI system in scope · **HITL on fail**: yes

## Must-haves (fail if absent)
- The classification tree walked explicitly: AI-system definition → prohibited check → high-risk (Art. 6 + Annex III / Annex I) → GPAI → transparency tier.
- Role classified (provider / deployer / importer / distributor) — duties differ.
- Applicability dates stated (the Act phases in; temporal tags mandatory).

## Scored dimensions (0–1; pass ≥ 0.7 all, revise ≥ 0.5 any, fail < 0.5 any)
| Dimension | Weight | What good looks like |
|---|---|---|
| Tier justification | 0.30 | Classification grounded in the system's actual function and Annex categories, with the closest-call alternative named |
| Duty-set completeness | 0.30 | The applicable chapter's duties cataloged (risk-mgmt, data governance, logging, oversight, transparency…) for the classified role |
| Prohibited-practice diligence | 0.25 | Art. 5 categories checked seriously, not waved through; any proximity flagged ⇒ halt + veto |
| Temporal accuracy | 0.15 | Phase-in dates and pending guidance flagged with as-of markers |

## Verdict envelope
`pass` / `revise` / `fail` (+ Tribune's Veto rendered).
