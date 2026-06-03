---
description: "Ulpian-led regulatory scan — regime identification, article-level obligation catalog, obligation→control→evidence mapping, prioritized gap analysis, EU AI Act classification where AI is in scope, Janus screening where borders are crossed."
argument-hint: "<product / feature / activity / change to assess> [--regimes <list>] [--controls <path to control inventory>]"
---

# /regulatory-scan — Ulpian Maps the Obligations

Run `$ARGUMENTS` through the **regulatory-counsel** agent (Ulpian) per
`regulatory-mapping`.

## Procedure

1. **Frame** — jurisdictions and activities, justified not assumed
   (Table VIII).
2. **Regime list** — applicable regimes with applicability reasoning and
   temporal status (in force / phasing / pending).
3. **Obligation catalogs** — article-level, per the catalog format:
   obligation | addressee | trigger | deadline | penalty.
4. **EU AI Act tree** — if an AI system is in scope: full classification
   (prohibited check → high-risk → GPAI → transparency tier), role
   classification (provider vs. deployer), duty set, applicability dates.
   Feeds eu-ai-act-classification@1 (hitl_required).
5. **Control mapping** — obligation → control **that exists** → evidence.
   No control inventory provided ⇒ `[CONTROL UNKNOWN — verify]`; gaps are
   findings.
6. **Trade overlay (Janus)** — cross-border elements ⇒ `export-controls`
   sub-agent: screening protocol + classification triggers. Unresolved
   exposure ⇒ gatekeeper halt.
7. **Gap prioritization** — scored; remediate-now / quarter-plan / backlog.
8. **Horizon scan** — pending changes, consultations, enforcement trends;
   re-assessment trigger date.
9. **Verification** — every regime citation through Tribonian with
   as-of markers.
10. **Gates & file** — compliance-coverage@1 (hitl_required) +
    citation-integrity@1; Risk Memo / obligation catalog to
    `output/regulatory/<topic>-<date>.md`.

## Output contract

Privilege banner · regime table with applicability reasoning · obligation
catalogs · control map with honest gaps · prioritized remediation ·
AI-Act classification (if in scope) · horizon notes · authorities
(temporally tagged).
