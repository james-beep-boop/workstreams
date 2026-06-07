# ARES Lesson Library — Build Progress

Tracker for the SHEQL lesson-plan platform. For requirements and architecture, defer to **`SPEC.md`** in the `Lesson3` repo.

**Last updated:** 2026-06-07

> **Major change (June 2026):** the platform was rewritten from scratch. The Laravel/Filament build (**Lesson2**) is **superseded**; the active project is **Lesson3** (Node/TypeScript + Payload CMS), which reuses the CBE generation system's own DOCX generator for high-fidelity export. Rationale is in `Lesson3/SPEC.md` §0.

---

## Active project — Lesson3 (Node / Payload)

**Repo:** https://github.com/james-beep-boop/Lesson3

### Done
- Architecture decided: Node/TS single runtime, Payload CMS (Postgres), embedded CBE generator for DOCX/PDF.
- Content model decided: structured **sub-strand bundle** (`META, UNIT, LESSONS[], FINAL_EXPLANATION, SUMMARY_TABLE`) → three generated documents.
- Editing model decided: edit the data not the document; plain-text fields; field-level RBAC; admin-screen-first, custom editor only if needed; live preview as the one early custom piece.
- Versioning model decided: Payload native versions + semver + official-version pointer; immutable snapshots; ingest as v1.0.0.
- Generator contract documented (field→paragraph/bullet rules; controlled phase vocabulary; deterministic regeneration).
- Repo created with full docs: `SPEC.md`, `CLAUDE.md`, `AGENTS.md`, `README.md`, `USER_GUIDE.md`, `docs/EXTERNAL-DEPENDENCIES.md`.

### Not started (next steps)
1. Scaffold the Payload + Postgres project.
2. Refactor the CBE generator's `generateOne()` to accept a data object; embed it in-process.
3. **Fidelity proof:** ingest the verified `bio_1_4` sub-strand → regenerate → diff against the approved `Chemicals_of_Life` DOCX.
4. Model the sub-strand bundle as native Payload nested fields with field-level access control.
5. Ingest pipeline (`.js` → JSON extraction, never execute) creating v1.0.0.
6. Live "Preview as Word/PDF" action.
7. Roles/subject-grades, taxonomy, auth.
8. Decide whether favorites / messaging / deletion-request workflows carry over.
9. Operations: error tracking, automated off-site backups, CI/CD, rate limiting.

---

## Legacy — Lesson2 (Laravel / Filament), superseded — reference only

**Repo:** https://github.com/james-beep-boop/Lesson2 · **Live (legacy):** https://www.sheql.com

Preserved as-is. Was a functional app (auth, roles, family/version model, compare, favorites, deletion requests, messaging, PDF + DOCX export, Ask-AI and Swahili-translation preview, admin panel, DreamHost deploy pipeline). Not extended further; no code is ported to Lesson3 — only the domain rules carried into `SPEC.md`.

The in-flight "Toast UI markdown editor" workstream and the persisted-Swahili-translation work are **abandoned** with the rewrite (the Markdown content model they depended on is gone).
