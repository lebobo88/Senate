# Senate ↔ TheEights Integration

TheEights is the memory substrate and evolution gate beneath the
constellation. The Senate uses it for precedent (*stare decisis*) and is
governed by it for any change to itself. **All usage is optional at
runtime** (AGENTS.md §6): absent TheEights, the Curia operates file-local
and the Tables still bind.

## Memory discipline

- **Namespace**: domain `legal`, scopes `["team:senate", <matter scopes>]`.
- **Recall** (movement 2 of the Curia workflow): `eights.memory.search` /
  `recall` on the matter's objective before deliberating.
- **Encode** on matter close: the DECISION_RECORD summary (never the full
  privileged record into broad scopes — Tables I & X).

### Cell mapping (the trigrams as legal memory)

| Cell | Trigram | Senate usage |
|---|---|---|
| **Dui** ☱ (Lake/Joy) | remembered wins | **Precedent — *stare decisis***: concluded matters, settled positions, playbook deviations that worked |
| **Kan** ☵ (Water/Danger) | risk | Legal-risk findings, refusals (Table XI), fabrication breaches, veto events |
| **Gen** ☶ (Mountain/Stillness) | constraints | Standing constraints adopted (jurisdictional rules, playbook walk-aways, regime floors) |
| **Li** ☲ (Fire/Clarity) | hot attention | Open matters awaiting the Tribune; deadlines running |

## Evolution governance (changes to the Senate itself)

Per TheEights' Autogenesis Resource Model and the cross-project risk
conventions:

| Resource | kind | risk_class | Policy |
|---|---|---|---|
| The squad (squad.yaml, roster) | `squad` | **critical** | **frozen** — legal/governance squads are critical-frozen by convention |
| Jurist agents | `agent` | high | hitl-only |
| Skills | `skill` | **high** (not the default low — legal content) | hitl-only |
| Commands | `command` | medium | hitl-only |
| Rubrics (gate rubrics) | `rubric` | **critical** | frozen (eval rubrics may not be mutated by the system they evaluate — TheEights invariant 7) |
| CONSTITUTION.md (Twelve Tables) | `constitution` | critical | frozen; amendment only via operator-signed unfreeze → propose_amendment → HITL → re-attestation (Table XII) |

Flow: `eights.evolution.register` each resource → any change via
`propose` → `evaluate` → HITL → `commit`. The Senate never self-amends;
proposals about the Senate may *originate* anywhere, but TheEights issues
the verdict and the human approves.

## Audit

Venue for Table VII at ecosystem scale: veto events, refusals, and
fabrication breaches are audit-relevant; where the audit surface is
present, log them (Kan cell). The artifact in `output/` remains the
durable record regardless.

## Constitution attestation

Where the attestation surface is present, the Senate attests its
CONSTITUTION.md hash at session start (`eights.constitution.attest`
pattern) alongside Hydra's. Mismatch ⇒ halt and surface (Table XII).
