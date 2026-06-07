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

- **MaryMargaret Welch**
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

- Online ARES digital educational materials demo: https://demo.aresedu.dev

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

- **What it is:** A platform to store, version, and distribute AI-generated lesson plans.
- **Status:** Early development; not yet in production use.
- **Website (temporary):** https://SHEQL.com
- **GitHub:** https://github.com/james-beep-boop/Lesson2
- **Stack:** Laravel 13, Filament 5, Livewire 4, Tailwind CSS 4, MariaDB, Laravel AI SDK, PHP 8.4+
- **Hosting:** DreamHost for V1 only; not a long-term solution
- **Codebase owner:** David exclusively

### Architecture notes

- V1 is online-only; schools must connect to DreamHost to access lesson plans.
- The system must eventually work offline - see decisions.md
- AI suggestions are controlled by the `AI_SUGGESTIONS_ENABLED` flag.

### Related notes

- GitHub channel integration, when wired, will turn PR and issue threads into conversations.
