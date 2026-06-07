# Update Recommendations

> **Retired (June 2026).** This file held dependency-update guidance for the **Lesson2** Laravel/Filament stack, which has been **superseded** by the **Lesson3** Node/Payload rewrite. The Laravel-specific recommendations below no longer apply and are kept only as historical context.

---

## Current dependency strategy (Lesson3, Node / Payload)

- **Pin versions and upgrade deliberately.** Payload 3 ships weekly and is Next.js-coupled — do not ride the release train. Upgrade as a discrete, tested task.
- **Treat the CBE generator (`docx` / `cbe-generation-system`) as a fidelity-critical dependency.** Pin it to a known commit; any upgrade is a deliberate, output-verified change (regenerate a known sub-strand and diff against its approved DOCX).
- Verify against installed source/official docs before coding; trust installed source over memory.
- Establish the Node toolchain choices (test runner, lint/format) and record them in `Lesson3/AGENTS.md`.

---

## Historical — Lesson2 (Laravel), no longer actionable

The original guidance was to defer dependency updates until after a Toast UI editor change, and specifically to hold `jfcherng/php-diff` (used in the old `DiffService.php`) and `phpunit/phpunit`. The Toast UI work and the entire Laravel stack are abandoned, so this is moot. The Lesson2 repo remains pinned at its last working versions for reference; no further updates are planned there.
