---
name: regulatory-mapping
description: "Ulpian's method — obligation catalogs, obligation→control→evidence mapping, gap prioritization, the EU AI Act classification tree, MiCA/MiCAR orientation, sectoral regime index (SOX/HIPAA/FCPA), sanctions/export trigger checklists, and horizon scanning."
allowed-tools:
  - Read
  - Write
  - Glob
  - Grep
---

# Regulatory Mapping

## Obligation Catalog Format

For each applicable regime, catalog at article level:

```
| Regime | Provision | Obligation (verb + object) | Addressee | Trigger | Deadline | Penalty exposure |
```

Rules: obligations are quoted or tightly paraphrased with pin cites
(Tribonian tags currency); conditional obligations carry their trigger
explicitly; "best efforts"-grade duties are flagged as judgment-dependent.

## Obligation → Control → Evidence Mapping

```
| Obligation (ref) | Control that satisfies it | Control owner | Evidence | Status |
```

**The Ulpian rule:** the control column names a control that EXISTS.
Status ∈ `mapped` / `partial` / `GAP` / `[CONTROL UNKNOWN — verify]`.
Inventing a control to complete a row is the regulatory equivalent of a
fabricated citation.

## Gap Prioritization

Score each gap: enforcement probability (30%) × penalty severity incl.
personal/criminal exposure (25%) × remediation cost+time (20%) × detection
likelihood (15%) × reputational amplification (10%).
≥3.5 remediate-now · 2.5–3.4 quarter-plan · <2.5 backlog-with-owner.
Feeds `compliance-coverage@1`.

## EU AI Act Classification Tree

```
Is it an AI system (Art. 3(1): machine-based, infers from input, generates outputs)?
├── No → out of scope (document why)
└── Yes
    ├── Prohibited practice (Art. 5: manipulation, social scoring,
    │   untargeted scraping, real-time remote biometric ID…)? → STOP + veto
    ├── High-risk (Art. 6 + Annex III: employment, credit, essential
    │   services, law enforcement…, or Annex I product-safety component)?
    │   → Ch. III duties: risk-mgmt system, data governance, technical
    │     docs, logging, transparency, human oversight, accuracy/robustness;
    │     deployer duties distinct from provider duties — classify the role
    ├── GPAI model? → Ch. V: technical docs, copyright policy, training-data
    │   summary; +systemic-risk duties above compute threshold
    ├── Limited-risk (chatbots, synthetic content)? → Art. 50 transparency
    └── Minimal → voluntary codes
```

Always record: role (provider/deployer/importer/distributor), tier,
applicable duty set, and applicability dates (the Act phases in — temporal
tags mandatory). Feeds `eu-ai-act-classification@1`.

## MiCA/MiCAR Orientation (crypto-assets, EU)

Token taxonomy first: ART (asset-referenced) / EMT (e-money) / other
crypto-asset (utility) — each with its own whitepaper, authorization, and
conduct duties; CASP licensing for service providers; market-abuse rules
across the board. Non-compliant stablecoin delisting precedent noted.
Detailed analysis routes to the regime catalog with current-text
verification.

## Sectoral Index (route-to-depth markers)

- **SOX** — ICFR, §302/906 certifications, auditor independence; route
  control testing to CCO surface.
- **HIPAA** — PHI: covered-entity/business-associate analysis, Security
  Rule safeguards, BAA paper (with Angerona).
- **FCPA / UKBA** — anti-bribery: third-party diligence, facilitation
  payments (banned under UKBA), books-and-records.
- **Sanctions/Export (Janus's checklists)**:
  - *Screening protocol*: counterparty → beneficial ownership (50% rule) →
    destination → end-use red flags (evasive answers, freight-forwarder
    end users, transshipment hubs, cash above market).
  - *Classification triggers*: encryption, dual-use Annex I categories,
    AI/compute thresholds, military/space nexus.
  - Output defines the screening to run against CURRENT lists — never
    certifies clearance from memory (Phase-1 limits).

## Horizon Scanning Discipline

Each regulatory matter notes: pending amendments to applied regimes,
consultation windows open, enforcement-trend signals, and a
re-assessment trigger date. Unknown ⇒ `[HORIZON UNSCANNED]` — silence is
not stability.

## Required Logging

Regime list with applicability reasoning · catalog coverage (articles
mapped vs. total) · gap register with scores · as-of statement for every
regime text relied on.
