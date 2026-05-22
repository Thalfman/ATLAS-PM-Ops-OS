# MASTER_PLAN.md

## Plan purpose

This master plan defines how ATLAS PM/Ops OS will be built from a local folder into a usable PM/Ops operating system. The system is intentionally Markdown-first and lightweight. It should produce practical artifacts before any automation is considered.

## Build rules

1. Do not overbuild.
2. Do not invent employer-specific details.
3. Do not use real employer data.
4. Use synthetic, public, generic, or fictional examples only during pre-start work.
5. Design Gemini-first but platform-agnostic workflows.
6. Preserve migration paths to future approved enterprise systems.
7. Keep humans accountable for decisions, approvals, commitments, and official communications.
8. Use `MASTER_CONTEXT.md` and `SESSION_HANDOFF.md` as continuity anchors.
9. End significant work by updating `09_HANDOFFS/SESSION_HANDOFF.md`.
10. Do not add package dependencies, frontend code, backend code, databases, APIs, deployment configs, or app scaffolding unless explicitly requested later.

## Phase structure

| Phase | Name | Primary outcome |
|---:|---|---|
| 0 | Project Setup and Operating Rules | Safe scaffold, starter files, operating rules, and handoff baseline. |
| 1 | Master Context and Continuity System | Hardened context, session protocol, and repeatable continuation method. |
| 2 | Roadmap and Artifact Backlog | Prioritized artifact backlog tied to onboarding and PM/Ops value. |
| 3 | Governance and Tool Approval Strategy | Safe AI use model, approval questions, and migration boundaries. |
| 4 | Workflow Library | Practical PM/Ops workflows for reporting, actions, risks, issues, schedules, finance, and knowledge capture. |
| 5 | Prompt Library | Gemini-first prompt patterns for safe, human-reviewed PM/Ops support. |
| 6 | First-Week Readiness Kit | Discovery scripts, listening plan, value map, and clearance-limited onboarding approach. |
| 7 | Synthetic Demo Pack | Fictional demos that show AI-enabled PM/Ops value without employer data. |
| 8 | Microsoft Project and Schedule Integrity Track | Schedule health review patterns, variance narratives, and schedule-control templates. |
| 9 | EVM, Finance, and Project Accounting Track | Variance explanation support, reconciliation narratives, and project accounting controls. |
| 10 | SOP and Lessons Learned Track | SOP drafting method, lessons learned capture, and knowledge reuse workflow. |
| 11 | Employer Migration Plan | Approved-tool migration path from local templates to enterprise systems. |
| 12 | Final Operating System Review | Coherent operating system review, gaps, readiness assessment, and next operating rhythm. |

## Phase 0 scope

Phase 0 creates the requested folder structure and useful starter files. It establishes the baseline rules, safety constraints, major milestones, backlog, starter workflows, starter prompts, governance notes, templates, synthetic demo, decision log, and local skills.

### Phase 0 deliverables

- `README.md`
- `00_MASTER_CONTEXT/MASTER_CONTEXT.md`
- `01_MASTER_PLAN/MASTER_PLAN.md`
- `02_ROADMAP/ROADMAP.md`
- `03_BACKLOG/ARTIFACT_BACKLOG.md`
- `04_WORKFLOWS/WORKFLOW_LIBRARY.md`
- `05_PROMPTS/PROMPT_LIBRARY.md`
- `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`
- `07_TEMPLATES/FIRST_WEEK_DISCOVERY_SCRIPT.md`
- `07_TEMPLATES/EXECUTIVE_NARRATIVE.md`
- `08_SYNTHETIC_DEMOS/SYNTHETIC_STATUS_PACK_DEMO.md`
- `09_HANDOFFS/SESSION_HANDOFF.md`
- `09_HANDOFFS/SESSION_HANDOFF_TEMPLATE.md`
- `10_DECISION_LOG/DECISION_LOG.md`
- `skills/atlas-planner/SKILL.md`
- `skills/atlas-artifact-writer/SKILL.md`
- `skills/atlas-session-handoff/SKILL.md`

### Phase 0 acceptance criteria

Phase 0 is complete when:

- All requested folders and files exist.
- Starter files are useful and structured, not empty placeholders.
- Safety boundaries are visible in the master context, governance notes, and handoff.
- The system clearly reflects Tom's AI integration value proposition.
- The system remains Markdown-first and does not create software scaffolding.
- `SESSION_HANDOFF.md` includes current status and the next best prompt.

## Near-term build sequence

### Session A: Phase 0 scaffold (complete)

Create the initial repository structure and starter files. Avoid depth where it would create false specificity. Include enough content for the next session to continue without restating context.

### Session B: Phase 1 continuity hardening (complete)

Refine `MASTER_CONTEXT.md` and `SESSION_HANDOFF_TEMPLATE.md`. Define the exact session-start and session-end protocols (including mode-gated commit and chat-only paste requirements) and the precedence rule for resolving conflicts between durable context and current status. Local skill files reviewed and left as-is; revisit in Phase 4 once workflow patterns stabilize (see A-0029 in the backlog).

### Session C: Phase 2 roadmap and artifact backlog (in progress)

Update `02_ROADMAP/ROADMAP.md` to cover Phases 0 through 12 with purpose, key files, PM/Ops outcomes, AI integration relevance, safety and governance considerations, completion criteria, and dependencies. Update `03_BACKLOG/ARTIFACT_BACKLOG.md` to a single ordered list with the standard field set (ID, artifact, category, phase, priority, purpose, intended user, data sensitivity posture, target environment assumption, human review point, status, notes/dependencies) across the standard categories.

### Session D: Phase 3 governance and approval strategy

Turn governance notes into an approval-ready framework: data sensitivity decision model, tool approval strategy, human review and auditability model, AI conversation guide, and a prompt and output retention note. Phase 4 workflows and Phase 5 prompts must wait on this so they can inherit a consistent envelope.

## Definition of done for any ATLAS artifact

An artifact is done when it:

- Names its purpose and intended user.
- Lists safe inputs and prohibited inputs.
- Defines output format.
- Includes a human review step.
- Avoids employer-specific assumptions.
- Can work in Gemini Enterprise without requiring non-approved tooling.
- Can later migrate to other approved systems.
- Is concise enough to be used in real PM/Ops work.

## Primary risks and controls

| Risk | Control |
|---|---|
| Accidentally mixing personal preparation with employer-sensitive material | Keep all pre-start examples synthetic/generic and mark employer-deployable material separately later. |
| Overbuilding technical infrastructure before workflows are proven | Stay Markdown-first until manual workflows are stable. |
| AI output being treated as authoritative | Require human review, source checks, and explicit uncertainty language. |
| Tool access assumptions being wrong | Make every workflow Gemini-first and platform-agnostic. |
| Clearance-limited onboarding reducing perceived value | Build safe discovery scripts, reporting templates, process maps, and synthetic demos that require no restricted access. |

## Operating cadence

For every meaningful work session:

1. Start with `MASTER_CONTEXT.md` and `SESSION_HANDOFF.md`.
2. Identify the current phase and target artifact (the roadmap and backlog are the catalog).
3. Make the smallest useful improvement.
4. Record decisions in `10_DECISION_LOG/DECISION_LOG.md` in the same session when they affect the system direction. Do not defer.
5. Update `09_HANDOFFS/SESSION_HANDOFF.md` before stopping, including the next best prompt.

## Source-of-truth alignment

`MASTER_CONTEXT.md` holds the phase list, protocols, and safety boundary; `MASTER_PLAN.md` (this file) holds the build rules, phase scope summaries, and definition of done; `ROADMAP.md` holds the per-phase detail (purpose, outcomes, AI relevance, safety, completion criteria, dependencies); `ARTIFACT_BACKLOG.md` holds the single ordered list of artifacts. When these disagree, `MASTER_CONTEXT.md` wins on durable identity and safety, `SESSION_HANDOFF.md` wins on current status and next best prompt, and `ROADMAP.md` and `ARTIFACT_BACKLOG.md` are the canonical sources for per-phase detail and per-artifact fields, respectively.
