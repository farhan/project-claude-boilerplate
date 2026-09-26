# project-claude-boilerplate

A reusable scaffold for Claude agentic development. Clone this into any new project to get a structured, context-disciplined Claude agent setup out of the box.

## What's included

| File / Directory | Purpose |
|---|---|
| `CLAUDE.md` | Always-loaded agent header — workflow rules, context discipline |
| `MEMORY.md` | Memory index — one line per stored memory, always in context |
| `memory/` | Memory files — loaded on demand when relevant |
| `.claude/settings.json` | Permissions baseline |
| `.claude/hooks/session-start.sh` | Bootstrap script injected at every session start |
| `.claude/commands/` | Custom slash commands (add your own `.md` files here) |
| `.claude/skills/` | Custom skills (add your own `.md` files here) |
| `docs/superpowers/workflow.md` | End-to-end story lifecycle (on-demand) |
| `docs/superpowers/agent-context-loading-policy.md` | Tier 1/2/3 loading policy (on-demand) |
| `docs/superpowers/specs/` | Project-scope design docs + template |
| `docs/superpowers/plans/` | Task/story execution plans + template |

## How to use

1. Clone or copy this repo into your project root.
2. Replace `<ProjectName>` in `CLAUDE.md` with your project name.
3. Add project-specific workflow rules to `CLAUDE.md`.
4. Optionally customise `session-start.sh` to bootstrap project context.
5. Start building — use `docs/superpowers/workflow.md` as your story lifecycle guide.

## Context discipline

This boilerplate enforces a tiered loading model:

- **Tier 1 (always loaded):** `CLAUDE.md`, `MEMORY.md`, SessionStart hook
- **Tier 2 (on demand):** specs, plans, source files, skills
- **Tier 3 (never):** `node_modules/`, build output, secrets, agent artifacts

See `docs/superpowers/agent-context-loading-policy.md` for the full model.
