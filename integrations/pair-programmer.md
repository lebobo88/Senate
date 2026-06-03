# Senate ↔ pair-programmer (The Forge)

The Forge builds; the Senate tells it what it may ship. Advisory
relationship — the Senate never blocks an engineering run directly; it
feeds gates and counsel.

## What the Senate supplies the Forge

1. **OSS license clearance** — Minerva's `ip-clearance` matrix backs the
   shared `open-source-license-compatibility` rubric (pp's
   security/license review surfaces and the Senate's gate use the same
   logic). Engineering question → `/ip-clearance <BOM> --type oss`.
2. **Contract-driven requirements** — Gaius extracts engineering-relevant
   obligations from customer/vendor paper (SLAs, data-processing terms,
   audit rights, deletion duties) into requirement lists pp teams can
   consume in spec stages.
3. **Privacy-by-design input** — Angerona's DPIA outputs map to pp's
   data-team and security-review-team stages (retention, minimization,
   subject-rights mechanics as NFRs).
4. **AI-controls counsel** — Ulpian's EU-AI-Act classification feeds pp's
   ai-controls-team (risk tier → required eval/HITL/documentation depth).

## What the Forge supplies the Senate

- Technical facts for legal analysis (architecture for DPIAs, dependency
  BOMs for clearance, data-flow diagrams for TIAs) — via artifacts, not
  improvised summaries.
- The forge's own gatekeepers (Cerberus/security, Charon/deploy) handle
  operational risk; the Senate handles *legal* risk. A deploy can be
  operationally safe and legally barred — or vice versa; the gates are
  independent.

## Mythological seam

The Forge's Cerberus guards the gate by force; the Senate's Janus guards
it by law. Mnemosyne (forge docs) records what shipped; Tribonian records
what authorized it. Same constellation, different jurisdictions.

## Practical wiring

No code dependency either direction. In Hydra, multi-squad routing handles
matters that need both (e.g., "ship feature X with GPL component Y" →
engineering + legal-compliance). Standalone, the human carries artifacts
across.
