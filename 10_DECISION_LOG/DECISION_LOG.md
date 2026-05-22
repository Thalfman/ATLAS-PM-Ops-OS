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
| D-0006 | 2026-05-22 | Place the Phase 0 through Phase 12 list inside `MASTER_CONTEXT.md`, not only in `MASTER_PLAN.md` or the prompt index. | The durable source of truth should carry the full phase plan so chat-only sessions can see it without browsing the repo. | `MASTER_CONTEXT.md` is the single place to read the phase plan; updates must be mirrored from `MASTER_PLAN.md` and the prompt index. | Active |
| D-0007 | 2026-05-22 | Add explicit Session-start and Session-end protocols to `MASTER_CONTEXT.md`. | Continuity must survive both local-agent and chat-only sessions; the protocols make the loop reproducible. | Every future ATLAS session begins and ends with the same explicit steps. | Active |
| D-0008 | 2026-05-22 | Define a precedence rule: `MASTER_CONTEXT.md` wins on durable identity and safety; `SESSION_HANDOFF.md` wins on current status and the next best prompt. | Eliminates ambiguity when the two files appear to disagree. | Future sessions resolve conflicts deterministically without restarting. | Active |
| D-0009 | 2026-05-22 | Expand `SESSION_HANDOFF_TEMPLATE.md` with source-of-truth review checklist, definition-of-done check (including a decision-log entry), AI tooling notes, and a parameterized next-best-prompt block. | Tightens the continuity loop and prevents drift between sessions. | Every handoff carries the same structured fields and a copy-paste-ready next prompt. | Active |
| D-0010 | 2026-05-22 | Gate the session-end commit step by mode: local-agent commits on a feature branch; chat-only hands Tom a copy-paste commit instruction as a human follow-up. | The previous unconditional commit step was unsatisfiable in chat-only mode. | The session-end protocol is internally consistent for both supported modes. | Active |
| D-0011 | 2026-05-22 | Require chat-only sessions to ask Tom to paste the relevant phase prompt and `DECISION_LOG.md` contents, in addition to `MASTER_CONTEXT.md` and `SESSION_HANDOFF.md`. | Phase work and decision logging cannot be run from memory in chat-only mode. | Chat-only sessions stay aligned with phase-specific instructions and avoid decision-ID collisions. | Active |
| D-0012 | 2026-05-22 | Leave the three `skills/*/SKILL.md` files unchanged in Phase 1. | They already align with the strengthened protocols; edits would be cosmetic and outside Phase 1 scope. | Skill files revisited only when Phase 2+ surfaces a concrete gap. | Active |

## Decision entry template

| ID | Date | Decision | Rationale | Impact | Status |
|---|---|---|---|---|---|
| D-XXXX | YYYY-MM-DD | [Decision] | [Why] | [What changes] | Proposed/Active/Retired |
