---
description: "Angerona-led privacy assessment — DPIA and/or transfer impact assessment per the privacy-frameworks templates, regime matrix applied, SCC selection where transfers exist. Gatekeeper: halts on unexamined cross-border exposure."
argument-hint: "<processing activity / data flow / system description> [--regimes gdpr,ccpa,appi,...] [--transfer]"
---

# /privacy-assess — Angerona Examines the Flow

Run `$ARGUMENTS` through the **privacy-counsel** agent (Angerona) per
`privacy-frameworks`. Mirrors Workflow 2 of the research doc (data-transfer
planning).

## Procedure

1. **Data inventory** — categories, subjects, purposes, lawful bases,
   retention, recipients, systems. Unknowns ⇒ `[UNMAPPED — obtain from
   data owner]`.
2. **Regime identification** — by subject location, controller location,
   and processing context (Table VIII); strictest applicable regime sets
   the floor.
3. **DPIA** — if triggered (high-risk processing) or requested: full
   template (necessity/proportionality → risks → mitigations → residual
   verdict).
4. **TIA** — if any cross-border flow: transfer map → mechanism → SCC
   module selection tree → supplementary measures → APPI Art. 16 path for
   Japan flows.
5. **Anonymization honesty test** — applied to any "anonymized" claim.
6. **Specialist pulls** — regulatory overlay (AI training on personal
   data, sectoral rules) → `regulatory-counsel` (Ulpian); sanctions-exposed
   destinations → `export-controls` (Janus).
7. **Verification** — authorities through Tribonian (EDPB guidance and
   adequacy decisions get temporal tags).
8. **Gate & verdict** — gdpr-art-25-privacy-by-design@1 (hitl_required);
   verdict proceed / proceed-with-mitigations / **halt-for-veto**. As
   gatekeeper, Angerona's halt renders the Tribune's Veto and stops.
9. **File** — DPIA/TIA Format to `output/privacy/<topic>-<date>.md`.

## Output contract

Privilege banner · data map · regime analysis (which regime drives what) ·
risk scores · mitigations + SCC selection · residual-risk verdict ·
re-assessment triggers · authorities.
