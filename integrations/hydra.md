# Senate ↔ Hydra Integration

The Senate is Hydra's **`legal-compliance`** squad — the **Curia Crown**,
fourth crown beside Executive, Forge, and Garland. `entrypoint:
claude-skill`; the adapter invokes `/senate` with the inbound envelope.

## Squad registration

- Hydra side: `<hydra>/squads/legal-compliance/squad.yaml` (active,
  claude-skill, `source_pack` → this repo) + `heads.yaml` (Curia cathedral
  overlay, `crown: curia`).
- Senate side: root `squad.yaml` + `heads.yaml` (canonical roster).
- MCP shim: `<hydra>/mcp_servers/senate/` exposes `senate.roster.list`,
  `senate.agent.get`, `senate.skill.list/get`, `senate.command.list/get`,
  `senate.output.write/read`, `senate.ping` (the `_pack_shim` pattern;
  root override via `HYDRA_SENATE_ROOT`).

## Router fingerprints

`hydra_core/router.py:_KEYWORDS["legal-compliance"]` — regulatory terms
(gdpr, ccpa, hipaa, eu ai act, sox…), contractual (contract, nda, msa,
redline, clause, indemnification…), IP (license, trademark, patent,
copyright, infringement), disputes (lawsuit, litigation, dmca), trade
(sanctions, export controls), plus mythic names (senate, curia, papinian,
ulpian, gaius, cicero, tribonian, angerona, scaevola) — Garland precedent
for mythic routing keys.

Accepted overlap: deal vocabulary (merger, due diligence, m&a) also
fingerprints `executive` ⇒ multi-squad routing on deal work is correct
behavior, not a bug.

## Envelope contract

| Direction | Types | Notes |
|---|---|---|
| **Accepts** | `HANDOFF`, `C_SUITE_DECISION_PACKET`, `PRD`, `CREATIVE_BRIEF` | validate via `hydra_core.schemas.validate_envelope`; preserve `parent_id`; resolve `context_refs` MemoryRefs rather than expecting inline blobs |
| **Emits** | `DECISION_RECORD` | `dissenting_opinions` populated verbatim (Table IX) — Hydra's synthesis judge sees real dissent |
| **Emits** | `HITL_REQUEST` | the Tribune's Veto; rendered per Hydra's `hitl-protocol` (verbatim, no paraphrase, default reject) |

PII redaction at the boundary (Table X): apply
`governance.redact_for_squad_boundary` semantics on anything leaving the
squad.

## Gates & judging

Squad gates (squad.yaml): `citation-integrity@1`, `aba-512-ethics@1`
(always, HITL on fail), `gdpr-art-25-privacy-by-design@1`,
`eu-ai-act-classification@1`, `compliance-coverage@1` (HITL),
`open-source-license-compatibility@1`. Hydra's judge registry carries
these rubric ids; `hydra_core/judge/policy.yaml` already enables
`legal-compliance`.

`best_of_n: 0` in v1 — Hydra's best-of-N rubric selection has no legal
branch yet. The Law of Citations provides multi-opinion judgment *inside*
the squad; Phase 2 adds the judge-router branch and turns best-of-N on.

## Constitution relationship

Hydra's CONSTITUTION.md is the immortal head of the whole; the Senate's
Twelve Tables bind this squad specifically and are stricter in-domain
(e.g., Table II's UPL lines, Table III's fabrication protocol). On
conflict: Hydra's refusals + the Tables are cumulative — both apply; the
stricter rule wins. Hydra refusal #9 ("Themis refuses actions out of
regulatory compliance") is the executive-crown statement of what this
entire squad operationalizes.

## Sibling squads

Xenia (the customer-support **Hearth**) is now an **active** squad — an
11-agent support crew with approval-gated execution under WS-AUTH — having
followed the same stub→active path the Senate's promotion templated (see
Hydra's `docs/constellation/exec-memos/cto.md` roadmap item: "Promote one
stub squad (legal-compliance) to active"). The Senate is Xenia's
legal-review depth for regulated-claim escalations; see
`integrations/xenia.md`.
