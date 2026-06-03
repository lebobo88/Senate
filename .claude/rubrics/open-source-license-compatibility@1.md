# Rubric: open-source-license-compatibility@1

**Kind**: ip · **Gate**: matters with OSS components in scope · **HITL on fail**: on fail

## Must-haves (fail if absent)
- Every in-scope component carries a license identification (or `[LICENSE UNIDENTIFIED]` flag — itself a finding).
- Copyleft-boundary analysis present for any GPL-family component (what counts as one program — analyzed, not assumed).
- AGPL in a network-service stack flagged Critical if present.

## Scored dimensions (0–1; pass ≥ 0.7 all, revise ≥ 0.5 any, fail < 0.5 any)
| Dimension | Weight | What good looks like |
|---|---|---|
| Matrix correctness | 0.30 | Compatibility verdicts match the matrix (inbound license × use mode); version specificity (v2-only vs v2+) respected |
| Obligations inventory | 0.30 | Notices, license texts, source offers, modification statements cataloged per component |
| Boundary analysis depth | 0.25 | Linking/process/derivative analysis articulated for copyleft components |
| Remediation actionability | 0.15 | Incompatibilities end in options: replace / isolate / comply / relicense |

## Verdict envelope
`pass` / `revise` / `fail`.
