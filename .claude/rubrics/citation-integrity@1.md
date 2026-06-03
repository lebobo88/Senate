# Rubric: citation-integrity@1

**Kind**: legal · **Gate**: every Senate artifact · **HITL on fail**: yes (Table III)

## Must-haves (fail if absent)
- Zero fabricated authorities (an authority that does not exist or materially misstates its source ⇒ automatic FAIL + breach protocol).
- Every cited authority carries a verification tag (`[VERIFIED:source-in-matter]`, `[VERIFIED:well-established]`, or `[UNVERIFIED]`).
- The Phase-1 limits statement present ("verification performed without live legal-database access…").

## Scored dimensions (0–1; pass ≥ 0.7 all, revise ≥ 0.5 any, fail < 0.5 any)
| Dimension | Weight | What good looks like |
|---|---|---|
| Tag honesty | 0.30 | Tags match the epistemic reality; doubt resolved toward `[UNVERIFIED]` |
| Downgrade discipline | 0.25 | Load-bearing `[UNVERIFIED]` ⇒ conclusion marked *preliminary*; no silent full-weight use |
| Jurisdiction & temporal tagging | 0.25 | Every authority carries jurisdiction + validity status (or `[VALIDITY UNCONFIRMED]`) |
| Citation hygiene | 0.20 | Pin cites where source in record; quotes exact; secondary cited as secondary |

## Verdict envelope
`pass` / `revise` (named dimensions + fixes) / `fail` (+ Tribune's Veto rendered).
