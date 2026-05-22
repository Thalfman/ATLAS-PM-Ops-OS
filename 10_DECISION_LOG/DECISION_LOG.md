# DECISION_LOG.md

## Purpose

This log captures important ATLAS PM/Ops OS decisions so the project remains consistent across sessions. Record decisions that affect structure, safety posture, artifact direction, migration strategy, or operating rules.

## Decision log

| ID | Date | Decision | Rationale | Impact | Status |
|---|---|---|---|---|---|
| D-0001 | 2026-05-22 | Build ATLAS as a Markdown-first operating system, not an app. | The immediate need is PM/Ops structure, templates, prompts, workflows, and governance, not software infrastructure. | No package dependencies, frontend/backend code, APIs, databases, or deployment configs in Phase 0. | Active |
| D-0002 | 2026-05-22 | Treat Gemini Enterprise as the likely first approved AI tool while keeping workflows platform-agnostic. | The workplace may initially approve Gemini only, but workflows should migrate to other approved tools later. | Prompts and workflows avoid tool-specific assumptions where possible. | Active |
| D-0003 | 2026-05-22 | Use only synthetic, public, generic, fictional, or user-created non-proprietary examples during pre-start work. | The role is federal/defense-adjacent and may involve sensitive data after onboarding. | All starter artifacts avoid real employer data. | Active |
| D-0004 | 2026-05-22 | Make AI integration a primary value workstream, not a side topic. | Tom's AI expertise was identified during hiring as part of expected value. | Roadmap, backlog, workflows, and prompts emphasize practical AI-enabled PM/Ops improvements. | Active |
| D-0005 | 2026-05-22 | End significant work by updating `09_HANDOFFS/SESSION_HANDOFF.md`. | Continuity is critical for a durable operating system. | Handoff file becomes the current-state anchor for future sessions. | Active |

## Decision entry template

| ID | Date | Decision | Rationale | Impact | Status |
|---|---|---|---|---|---|
| D-XXXX | YYYY-MM-DD | [Decision] | [Why] | [What changes] | Proposed/Active/Retired |
