# Senate ↔ AgentSmith Integration

AgentSmith is the ecosystem's immune system — schema validation, anomaly
watching, quarantine. The Senate is a *subject* of Smith's inspection and
a *peer* in governance philosophy: Smith enforces structure; the Senate
counsels law. Optional at runtime; binding when present.

## Invariant deference (N1–N10)

The Senate defers to all ten Smith invariants. The ones that bite here:

- **N3 hitl_sovereignty** — aligns with Table IV: policy-breach HITLs are
  fail-closed. The Tribune's Veto and Smith's HITL sovereignty are the
  same covenant in two dialects.
- **N5 audit_completeness** — every Senate refusal and veto is
  audit-recorded (Table VII).
- **N6 least_privilege** — jurists carry the minimum tool grants
  (consilium members don't even hold eights-memory write).
- **N7 schema_compliance** — all envelopes validate against the
  cross-squad-message schemas; fail closed.
- **N10 venom_deference** — the Senate may *counsel* on a venom refusal
  appeal (cerberus-bridge), but never overrides Cerberus. Legal analysis
  of whether an action is lawful ≠ authority to perform it.

## Inspection compliance

Senate artifacts conform to the cross-project conventions Smith inspects:

- Agents: `name` (= filename slug), `description` ≤ ~200 chars, optional
  `model`/`maxTurns`/`skills`/`tools` — per the universal frontmatter.
- Skills: `name`, `description`, `allowed-tools`.
- Commands: `description`, `argument-hint`.
- Squad: the squad.template.yaml required surface (name, agents,
  fingerprints-via-Hydra-router, gates with ≥1 HITL gate — the Senate has
  five).

`/smith:inspect <artifact>` should pass on any Senate file; a Smith
inspection failure on a Senate artifact is treated as a defect here, not
an exception request there.

## Factory & scaffolding

New jurists/skills/rubrics for the Senate should be scaffolded via
`/smith:scaffold` (agent-factory-recipes) so stamps
(`generated_by/constitution_hash/risk_class`) and schema conformance come
free — then registered with TheEights per `integrations/eights.md`.

## Quarantine

If Smith quarantines a Senate artifact (drift, injection, anomaly), the
Curia does not argue with the immune system: the artifact is out of the
bench until the HITL ticket resolves. Papinian notes the reduced bench in
any deliberation run meanwhile (Table V — competence includes knowing
who's missing).

## The philosophical seam

Smith is *lex talionis* — structure enforced without judgment. The Senate
is *ius* — judgment within structure. Smith would quarantine a corrupted
jurist; the Senate would counsel whether the quarantine power itself is
being lawfully exercised. Both answer to the human (N3; Table IV) — and
neither can amend its own constitution (N4; Table XII).
