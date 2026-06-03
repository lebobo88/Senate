---
description: "Gaius-led contract review — full read, CUAD-style clause classification, risk-tiered redline report with alternative language. Pulls Angerona (data terms), Minerva (IP terms), Paulus (employment terms), Janus (cross-border) as the paper demands."
argument-hint: "<path to contract, or pasted contract text> [--counterparty <name>] [--posture buy|sell|mutual]"
---

# /contract-review — Gaius Reads the Paper

Run `$ARGUMENTS` through the **contract-counsel** agent (Gaius) per
`contract-redline-protocol`. This mirrors Workflow 1 of the research doc
(vendor contract review).

## Procedure

1. **Read everything** — the full contract and all provided exhibits.
   Referenced-but-missing exhibits ⇒ `[NOT PROVIDED — review incomplete]`.
2. **Governing law & venue first** (Table VIII).
3. **Classify & tier** — every clause into the taxonomy; risk tiers
   Critical/High/Moderate/Low with scores.
4. **Missing-clause checklist** — absence is risk; flag it.
5. **Specialist pulls** (sub-agents, only as the paper demands):
   - data-processing/personal-data clauses → `privacy-counsel` (Angerona)
   - IP ownership/license/OSS clauses → `ip-counsel` (Minerva)
   - employment/contractor terms → `employment-counsel` (Paulus)
   - cross-border performance, sanctions-exposed parties → `export-controls`
     (Janus)
6. **Alternative language** — primary + fallback for all Critical/High,
   insertable as drafted.
7. **Verification** — clause interpretations and any cited authority
   through `citation-verifier` (Tribonian).
8. **Gates** — citation-integrity@1, aba-512-ethics@1; plus
   gdpr-art-25-privacy-by-design@1 / open-source-license-compatibility@1
   if pulled in. HITL failures ⇒ Tribune's Veto.
9. **File** — Redline Report Format to
   `output/contracts/<topic>-<date>.md`.

## Output contract

Privilege banner · executive summary (the 3 must-wins) · clause table ·
ranked issues list with dispositions · alternative-language appendix ·
specialist findings · authorities.
