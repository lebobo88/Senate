# Senate ↔ AgentMesh (The Binding Layer)

AgentMesh is the **tenth** of the constellation — the thin, governed
**control plane** that binds the nine sibling systems together. Where the
Senate counsels law and AgentSmith enforces structure, AgentMesh does
neither: it **routes and observes**. It unifies the nine behind one
registry, one lifecycle supervisor, one observability plane, one federated
audit timeline, one external protocol edge, and one operator console — and
**enforces no governance of its own**. The Senate is an *enrolled member*;
AgentMesh is binding when present, optional at runtime (the Tables still
bind absent it).

## What AgentMesh provides

- **One registry** — SQLite `~/.agentmesh/state.db`; AgentMesh is the
  **sole writer** of `~/.hydra/backends.json` (the Senate's gateway
  backend entry is written there, not hand-edited).
- **One lifecycle supervisor** — Win32 Job Objects + crash-loop breaker +
  health probes; starts/stops the Senate MCP shim and watches its pulse.
- **One observability plane** — OTEL traces + structured logs across all
  systems.
- **One federated, read-only audit timeline** — stitched from
  TheEights / AgentSmith / Hydra chains (AgentMesh does not author audit
  records; it reads and orders them).
- **One protocol edge** — A2A (v0.3 / v1.0), REST, MCP-over-HTTP.
- **One operator web console**.

## Enrollment (root `mesh-manifest.yaml`)

The Senate enrolls by shipping a root
[`mesh-manifest.yaml`](../mesh-manifest.yaml) —
`apiVersion: agentmesh/v1`, `kind: SiblingManifest`, `metadata.id: senate`.
Enrollment is **fail-closed**: the manifest is validated against
`AgentMesh/mesh-manifest.schema.json`, and three checks must **all** pass
before the Senate joins the mesh:

1. **JSON-Schema validation** of the manifest itself.
2. **Constitution attestation** — the Twelve Tables hash, routed via
   TheEights (`eights.constitution.attest`, consumer `senate`) per the
   governance precedence; see `integrations/eights.md`.
3. **AgentSmith structural inspection** — the manifest + the Senate's
   artifact surface pass Smith's invariants; see `integrations/agentsmith.md`.

Any failure ⇒ the Senate does not enroll. There is no exception path; a
failing manifest is a defect to fix here, not an override to request there.

## What the manifest declares

| Field | Value | Source of truth |
|---|---|---|
| `runtime` | `python-langgraph`; Hydra `mcp_servers/senate` shim (`cwd` = Hydra) | `~/.hydra/backends.json` "senate" |
| `mcp.tools` | `senate.roster.list`, `senate.agent.get`, `senate.skill.list/get`, `senate.command.list/get`, `senate.output.write/read`, `senate.ping` | Hydra `mcp_servers/senate/server.py` |
| `healthProbe` | `senate.ping`, 20 s interval, 8 s timeout, 3-failure threshold | server.py |
| `lifecycle.startupDependencies` | `hydra` (Senate runs as Hydra's `legal-compliance` squad shim) | this repo |
| `audit.exportTool` | `senate.output.read` (retrieves legal work-product for audit stitching) | server.py |
| `governance.constitutionPath` | `../Senate/CONSTITUTION.md` (the Twelve Tables) | this repo |
| `governance.attestTool` | `senate.ping` (connectivity only; formal attestation via TheEights) | mesh-manifest.yaml |

## Health probe & lifecycle

AgentMesh's supervisor calls `senate.ping` on the declared interval; three
consecutive failures trip the probe, and the crash-loop breaker (threshold
5, 60 s window) guards restart storms. None of this touches Senate
*judgment* — a degraded shim means the squad is unreachable, never that a
deliberation's verdict changes. Papinian notes an unreachable bench the
same way he notes a quarantined jurist (Table V — competence includes
knowing who's present).

## Audit & attestation routing

AgentMesh's audit timeline is **read-only and federated**: it stitches the
Senate's `output/` artifacts (via `senate.output.read`) into the
cross-system view but originates no records. The durable legal record stays
in `output/` (Table VII), and formal audit federation + constitution
attestation route through **TheEights** per the governance precedence —
AgentMesh observes the result, it does not own it.

## The precedence seam

AgentMesh binds; it does not arbitrate. Authority stays in the chain
**TheEights → AgentSmith → Hydra**, and in-domain the Senate's own heads —
the **Tribune's Veto**, the **Law of Citations**, and the **Twelve
Tables** — remain wholly the Senate's. AgentMesh can route a matter to the
Senate and observe the DECISION_RECORD that comes back; it can never weigh
the opinions, break a tie, or lift a veto. The control plane carries the
message; the Curia decides the law.
