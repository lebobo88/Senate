---
description: "Informational — show the Curia roster, authorities, commands, gates, and constitution status. No deliberation; no output file."
argument-hint: "(no arguments)"
---

# /senate-roster — Who Sits the Curia

Read-only status command. Render:

1. **Constitution status** — `CONSTITUTION.md` present? Compute and show
   SHA-256 (first 12 hex). Missing ⇒ warn loudly.

2. **The roster table** — from `heads.yaml`: mythic | slug | authority |
   model tier | scope | parent (consilium). Present heads and consilium
   separately.

3. **Commands** — the 9 commands with one-line purposes
   (`.claude/commands/`).

4. **Gates** — the 8 rubrics (`.claude/rubrics/`) and which are
   hitl_required.

5. **Integration status** (best-effort, no hard failures — AGENTS.md §6):
   - Hydra shim reachable? (senate.ping if MCP tools are present)
   - eights-memory available?
   - Standalone mode otherwise: "The Curia stands alone; the Tables still
     bind."

6. **Recent matters** — last 5 artifacts under `output/` by date, with
   domain.

Render as a compact dashboard. Do not write any file.
