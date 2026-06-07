# Projects

This file is the shared project brief for Hermes, Nanoclaw, Codex, and other agents.
Read top to bottom before starting work. Earlier sections have higher priority.

## ARES Education — Organization

- **Full name:** African Ruggedized Education Solution (ARES)
- **Website:** https://areseducation.org
- **Mission:** Close the digital literacy gap for rural Kenyan K-12 students by deploying offline education servers with 350GB+ of content, including Khan Academy, Wikipedia, and Kenyan curricula. No internet or reliable electricity required.
- **Scale:** 45 systems installed in Laikipia County (2014–2025), serving about one-third of secondary schools.

### Key people

- **Mark Knittel** (`mark.knittel@gmail.com`)
  - Originator and organizer
  - Software developer for all ARES software except SHEQL
  - Fundraiser
  - Education content creator
- **David**
  - IT support
  - Sole developer of SHEQL

### Collaborators

These are ground-operations partners only. They help with training teachers and maintaining equipment, but are not involved in software development.

- Seavuria — https://www.seavuria.org
- Ol Pejeta Conservancy — https://www.olpejetaconservancy.org
- Tsavo Trust — https://tsavotrust.org
- Afretech Aid Society — https://www.afretech.org

### Demo

- Digital educational materials demo: https://demo.aresedu.dev
- Note: returns 403 from the container, but loads correctly in a browser.

---

## AI Lesson Plan Development — Current Priority

- **Lead:** Mark Knittel, working with Seavuria.
- **Purpose:** Use AI, primarily Claude, to create detailed lesson plans for Kenyan high school teachers.
- **Curriculum target:** Kenya’s Competency Based Curriculum (CBC), mandated nationwide by the Kenyan Department of Education.
- **Type of work:** Content creation, not software.
- **Output:** Structured, curriculum-compliant lesson plans deployed to teachers across Kenya.
- **Priority note:** This work is more strategically important than the SHEQL platform itself.

### CBE Generation System

- **GitHub:** https://github.com/markknit/cbe-generation-system
- **Purpose:** Core logic that generates the lesson plans
- **Access:** David now has direct access to the codebase
- **Relationship to SHEQL:** Generated lesson plans are stored and distributed via SHEQL

---

## SHEQL — Lesson Plan Platform

- **What it is:** A **versioned lesson-plan repository** — ingest CBE lesson plans from the generation system as v1.0.0, allow basic teacher editing with bulletproof version history, and export high-fidelity DOCX/PDF.
- **Status:** Clean-slate rewrite underway (**Lesson3**). The first build (**Lesson2**, Laravel/Filament/DreamHost) is superseded and preserved for reference.
- **Website (temporary):** https://SHEQL.com
- **GitHub:** https://github.com/james-beep-boop/Lesson3 (active) — supersedes https://github.com/james-beep-boop/Lesson2 (preserved, legacy)
- **Stack:** Node.js / TypeScript, Payload CMS, PostgreSQL. DOCX/PDF are produced by **reusing the CBE generation system's own Node generator** in-process (single runtime).
- **Hosting:** A Node-capable host (cloud VPS now; a local Node + Postgres box for offline later). DreamHost is retired.
- **Codebase owner:** David exclusively

### Architecture notes

- Lesson plans are **structured data** (a nested sub-strand bundle), not documents. The unit of content is a sub-strand, which generates three Word files (LessonSequence, FinalExplanation, SummaryTable).
- **High-fidelity DOCX is only achievable by reusing the CBE generator** — storing Markdown/HTML is lossy. This is why the platform is now built in the generator's runtime (Node), and why the Laravel V1 was rewritten.
- **Editing edits the data, never the document**; documents are regenerated on demand. Teachers edit plain-text fields; all formatting is owned by the generator.
- **Offline operation is a secondary goal**, addressed later by deploying the single Node + Postgres app to a local box — not a primary architectural driver.

### Related notes

- GitHub channel integration, when wired, will turn PR and issue threads into conversations.
