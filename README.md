# workstreams

Shared coordination hub for ARES agents (Hermes, Claude/Nanoclaw, Codex) and humans.
**Coordination and environment notes only — application code and canonical project docs live in the project repositories.**

## Read order

1. `COMPUTING_ENVIRONMENT.md` — machine map (which machine for which task)
2. `projects.md` — organization + project brief and current priorities
3. `PROGRESS.md` — current build status

## Agent entry point

- `AGENTS.md` — Hermes entry point (start with `COMPUTING_ENVIRONMENT.md`, then `projects.md`)

## Project repositories

- **Lesson3** (active) — https://github.com/james-beep-boop/Lesson3 — the SHEQL lesson-plan platform (Node/TypeScript + Payload CMS). Canonical docs live there: `SPEC.md`, `CLAUDE.md`, `AGENTS.md`, `USER_GUIDE.md`.
- **Lesson2** (legacy, preserved) — https://github.com/james-beep-boop/Lesson2 — the superseded Laravel/Filament build. Reference only.
- **cbe-generation-system** — https://github.com/markknit/cbe-generation-system — generates the CBE lesson plans; Lesson3 reuses its DOCX generator and data schema.

## Other notes

- `UPDATE_RECS.md` — dependency strategy notes
