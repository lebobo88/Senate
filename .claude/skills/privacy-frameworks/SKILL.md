---
name: privacy-frameworks
description: "Angerona's toolkit — regime matrix (GDPR, CCPA/CPRA, APPI, PIPEDA, UK GDPR), DPIA and TIA templates, SCC selection tree, APPI Article 16 analysis, breach-response clocks, and the anonymization honesty test."
allowed-tools:
  - Read
  - Write
  - Glob
  - Grep
---

# Privacy Frameworks

## Regime Matrix (orientation, not gospel — Tribonian tags currency)

| Question | GDPR/UK GDPR | CCPA/CPRA | APPI (Japan) | PIPEDA (Canada) |
|---|---|---|---|---|
| Lawful basis required | Yes (Art. 6; Art. 9 special) | No (opt-out model) | Purpose specification + consent for sensitive | Consent-centric |
| Transfer mechanism | Ch. V: adequacy / SCCs / BCRs + TIA | n/a (service-provider terms) | Art. 24/28: consent, equivalency, or safeguards (Art. 16 framework) | Comparable-protection accountability |
| DPIA trigger | Art. 35: high-risk processing | Risk assessments (CPRA regs) | PIA recommended | PIA expected (public sector mandatory) |
| Breach clock | 72h to authority (Art. 33) | "Expedient" + AG thresholds | PPC report + subject notice for defined breaches | RROSH test → report |
| Sanctions scale | 4% global turnover | Per-violation civil penalties | Administrative orders, criminal in egregious cases | CAD$100k/violation (reform pending) |

**Rule:** the strictest applicable regime sets the floor. State which regime
drives each requirement.

## DPIA Template (GDPR Art. 35-shaped, regime-adaptable)

1. **Processing description** — nature, scope, context, purposes; data
   categories; subjects; retention; recipients; systems.
2. **Necessity & proportionality** — purpose limitation, data minimization
   (could less data achieve the purpose? answer honestly), accuracy,
   storage limits, subject rights mechanics.
3. **Risk assessment** — per risk: source → harm → likelihood (1-5) ×
   severity (1-5); special-category and vulnerable-subject multipliers.
4. **Mitigations** — technical (pseudonymization, encryption, access
   control) and organizational (policies, training, contracts); residual
   score after each.
5. **Verdict** — proceed / proceed-with-mitigations / halt-for-veto;
   consultation-with-authority trigger check (residual high ⇒ Art. 36).

## TIA Template (Schrems-II discipline)

1. Transfer map: exporter → importer(s), onward transfers, data categories.
2. Mechanism: adequacy? If not → SCCs (module selection below) / BCRs /
   derogations (narrowly).
3. Destination-law assessment: government-access regimes, redress
   availability — `[ASSESSMENT REQUIRED]` where current country analysis is
   needed (Phase-1 limits).
4. Supplementary measures: encryption-in-transit-and-rest with
   exporter-held keys, pseudonymization before transfer, split processing.
5. Verdict + re-assessment trigger (law change, new onward transfer).

### SCC Module Selection Tree

```
Exporter is controller?
├── Importer controller   → Module 1 (C2C)
└── Importer processor    → Module 2 (C2P)
Exporter is processor?
├── Importer (sub)processor → Module 3 (P2P)
└── Importer controller     → Module 4 (P2C)
+ Docking clause for multi-party; UK: IDTA or UK Addendum; CH: FDPIC adaptations.
```

## APPI Article 16 / Cross-Border (Japan) Analysis

1. Is the recipient in a country with equivalency (EU/UK currently
   designated — verify currency)?
2. If not: informed consent naming the destination regime, OR
   importer-side "equivalent standards" via contract + ongoing oversight
   (Art. 28 measures: annual confirmation, publication duties).
3. Document the chosen path; APPI's consent disclosures are specific —
   generic consent fails.

## Breach-Response Clocks (first 72 hours)

| Hour | Action |
|---|---|
| 0 | Contain; preserve evidence; open privileged channel (route litigation-hold to Cicero) |
| 0–24 | Scope: data categories, subjects, jurisdictions affected → regime matrix |
| 24–48 | Notification analysis per regime (GDPR 72h clock is running); draft authority notice |
| 48–72 | Authority notifications as triggered; subject-notice severity analysis; insurer notice |

## The Anonymization Honesty Test

"Anonymized" is claimed constantly and true rarely. Before accepting the
label: singling-out possible? linkability to other datasets? inference of
attributes? If any yes ⇒ it is *pseudonymized* (still personal data).
Aggregation with small cells (< ~10) ⇒ still re-identifiable. Write the
test result, not the label.

## Required Logging

Every assessment records: regimes applied and which drove each requirement,
data-map gaps (`[UNMAPPED]`), the verdict with residual scores, and re-
assessment triggers. Feeds `gdpr-art-25-privacy-by-design@1`.
