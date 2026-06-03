---
name: contract-redline-protocol
description: "Gaius's method — CUAD-style clause taxonomy, four-tier risk classification, playbook positions (primary/fallback/walk-away), alternative-language drafting rules, and the missing-clause checklist. Drives /contract-review and all commercial paper."
allowed-tools:
  - Read
  - Write
  - Glob
  - Grep
---

# Contract Redline Protocol

## Clause Taxonomy (CUAD-aligned, practical subset)

Classify every clause reviewed into one of:

**Structure & control**: parties/affiliates · term · renewal (auto-renewal
flagged) · termination for convenience/cause · change of control ·
assignment · subcontracting · order of precedence.

**Money**: fees & escalators · payment terms · taxes · audit rights ·
most-favored-nation · revenue/cost true-ups.

**Risk allocation**: limitation of liability (cap, basis, carve-outs) ·
indemnification (scope, procedure, baskets) · insurance · warranties &
disclaimers · force majeure.

**IP & data**: IP ownership · license grants (scope, exclusivity, field) ·
feedback clauses · data processing & security · confidentiality ·
publicity.

**Performance**: SLAs & credits · acceptance · deliverables · personnel ·
non-solicitation · compliance-with-laws · export/anti-bribery.

**Disputes & boilerplate**: governing law · venue/arbitration · notice ·
amendment · waiver · severability · entire agreement · survival.

## Risk Tiers

| Tier | Definition | Treatment |
|---|---|---|
| **Critical** | Uncapped/unbounded exposure, IP ownership loss, compliance breach built-in, unilateral counterparty control | Alternative language mandatory; escalation candidate |
| **High** | Materially off-market allocation, asymmetric rights, missing protective clause | Alternative language drafted; negotiate |
| **Moderate** | Off playbook but bounded | Fallback acceptable; note it |
| **Low** | Cosmetic/stylistic | Accept; do not spend negotiating capital |

Score per the clause-risk framework (contract-counsel agent): exposure 30%
× likelihood 25% × asymmetry 20% × estate precedent 15% × exit friction
10%.

## Playbook Positions

For each negotiated clause family, hold three positions:

- **Primary** — the opening position (e.g., LoL: mutual cap at 12 months'
  fees; carve-outs limited to confidentiality breach, IP infringement,
  gross negligence/willful misconduct).
- **Fallback** — pre-approved retreat (e.g., 2× fees super-cap for data
  breach).
- **Walk-away** — the line that triggers escalation, not concession (e.g.,
  uncapped indemnity for ordinary breach; assignment of pre-existing IP).

Deviations from playbook are recorded with reasons — they become precedent
for the contract estate (encode on close).

## Alternative-Language Drafting Rules

1. Draft in the contract's defined terms and style — a redline that
   re-voices the document gets rejected wholesale.
2. Smallest sufficient edit: surgical strikes over rewrites.
3. Every proposed clause is complete and insertable — no `[appropriate
   language]` placeholders.
4. Pair each Critical/High alternative with a one-line rationale the
   negotiator can say out loud.

## Missing-Clause Checklist

Absence is risk. Check for and flag missing: limitation of liability ·
indemnity (both directions) · termination rights · data-processing terms
(route to Angerona if personal data) · IP ownership/license back ·
confidentiality · governing law (Table VIII — its absence is a Critical
flag) · notice mechanics · survival.

## Required Logging

Each review records: clauses classified (N by tier), missing clauses
flagged, playbook deviations, cross-domain routings (privacy/IP/employment/
trade), and exhibits not provided. Feeds the Redline Report Format
(`curia-protocol` §2).
