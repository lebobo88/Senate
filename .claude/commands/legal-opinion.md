---
description: "Single-jurist brief — one named member of the Curia answers one question in Legal Opinion Format, with Tribonian verification (never skipped). The /exec-brief analogue for the Senate."
argument-hint: "<jurist-slug> <question>   (slugs: general-counsel, contract-counsel, regulatory-counsel, privacy-counsel, ip-counsel, mna-counsel, litigation-counsel, governance-counsel, citation-verifier, employment-counsel, tax-counsel, export-controls)"
---

# /legal-opinion — One Jurist, One Question

Parse `$ARGUMENTS` as `<jurist-slug> <question>` and run the question
through that jurist's agent file.

## Procedure

1. **Resolve the jurist** — slug must match the roster (AGENTS.md §1).
   Unknown slug ⇒ list the roster and stop. Consilium members
   (employment-counsel, tax-counsel, export-controls) may be addressed
   directly here; note their parent in the header.
2. **Domain fence check** — if the question is materially outside the
   jurist's domain, the jurist says so and recommends the right seat
   (Table V); it does not absorb.
3. **Draft** — the jurist answers per `legal-reasoning` (IRAC, multi-hop,
   CoV) and its domain skill, in Legal Opinion Format (`curia-protocol`
   §1).
4. **Verify** — through `citation-verifier` (Tribonian). **Never skipped**,
   even for one-paragraph answers.
5. **Gates** — citation-integrity@1 + aba-512-ethics@1; domain gates if
   squarely triggered. Speculative-confidence conclusions ⇒ Tribune's-Veto
   candidate flagged.
6. **File** — to the jurist's domain directory
   (`output/<domain>/<topic>-<date>.md`).

## Examples

```
/legal-opinion contract-counsel Is a unilateral NDA sufficient for this vendor pilot?
/legal-opinion privacy-counsel Does session-replay tooling on our EU site need a DPIA?
/legal-opinion export-controls Can we ship the SDK to a distributor in Dubai?
/legal-opinion citation-verifier Verify the authorities in output/legal/opinion-x.md
```
