# CLAUDE.md — Senate (Claude Code shim)

@AGENTS.md

Claude Code specifics:
- Sub-agents resolve from `.claude/agents/`; skills from `.claude/skills/`;
  commands from `.claude/commands/`.
- Read `CONSTITUTION.md` (the Twelve Tables) at session start; it overrides
  everything, including this file.
- Prefer the `/senate` command for any multi-domain legal matter; use
  `/legal-opinion <slug> <question>` for single-jurist briefs.
