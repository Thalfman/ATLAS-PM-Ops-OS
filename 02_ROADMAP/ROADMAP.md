# ROADMAP.md

## Roadmap purpose

This roadmap sequences ATLAS PM/Ops OS from safe scaffold to an employer-migratable operating system. Order matters more than the calendar. Dates are intentionally omitted until Tom has enough environment information to commit to one.

The roadmap is not a software product plan. It is a sequence of PM/Ops content deliverables (templates, workflows, prompts, dashboards, checklists, synthetic demos, governance notes, and operating rituals) that mature into a portable PM/Ops operating system.

## How to read this roadmap

For each phase, the roadmap captures:

- **Purpose** - what the phase exists to accomplish.
- **Key files or artifact areas** - where the work lives in the repo.
- **PM/Ops outcomes** - concrete value Tom should be able to demonstrate after the phase.
- **AI integration relevance** - how the phase advances responsible AI workflow integration.
- **Safety and governance considerations** - what must stay inside the hard safety boundary.
- **Completion criteria** - the operational test that ends the phase.
- **Dependencies and sequencing notes** - what must already be true.

## Status key

- **Complete** - usable starter version exists and has been hardened.
- **In progress** - active build area.
- **Planned** - sequenced but not yet built.
- **Deferred** - intentionally held until employer approvals or real environment details are available.

## Milestone roadmap (at a glance)

| Phase | Milestone | Status | Outputs (representative) |
|---:|---|---|---|
| 0 | Project Setup and Operating Rules | Complete | Folder scaffold, starter files, safety boundary, handoff baseline, phase prompt pack. |
| 1 | Master Context and Continuity System | Complete | Hardened `MASTER_CONTEXT.md`, session-start/end protocols, expanded handoff template, decision log entries D-0006 through D-0013. |
| 2 | Roadmap and Artifact Backlog | In progress | This roadmap, prioritized artifact backlog with per-artifact fields, alignment touch-ups to `MASTER_PLAN.md`. |
| 3 | Governance and Tool Approval Strategy | Planned | Strengthened governance notes, tool approval strategy, data sensitivity decision model, conversation guide for AI integration. |
| 4 | Workflow Library | Planned | Reusable PM/Ops workflow cards for reporting, actions, risks, issues, schedule, finance, and knowledge capture. |
| 5 | Prompt Library | Planned | Gemini-first prompt patterns mapped to workflow steps, with safe-input contracts and human review points. |
| 6 | First-Week Readiness Kit | Planned | Discovery script, listening plan, onboarding questions, clearance-limited value plan, leadership-update template. |
| 7 | Synthetic Demo Pack | Planned | Fictional status pack, schedule variance demo, action tracker demo, discrepancy triage demo. |
| 8 | Microsoft Project and Schedule Integrity Track | Planned | Schedule-health checklist, variance narrative template, cross-tool mismatch workflow on synthetic schedules. |
| 9 | EVM, Finance, and Project Accounting Track | Planned | EVM variance support prompts, reconciliation narrative patterns, accounting discrepancy workflow on synthetic finance. |
| 10 | SOP and Lessons Learned Track | Planned | SOP drafting workflow, lessons-learned capture, knowledge base template. |
| 11 | Employer Migration Plan | Deferred | Approved-tool migration plan once actual environment and policy boundaries are known. |
| 12 | Final Operating System Review | Deferred | End-to-end review, gap list, operating rhythm, maintenance plan. |

## Per-phase detail

### Phase 0 - Project Setup and Operating Rules

- **Purpose:** Stand up a safe, repeatable scaffold so future phases never restart from zero.
- **Key files or artifact areas:** `README.md`, `00_MASTER_CONTEXT/`, `01_MASTER_PLAN/`, `02_ROADMAP/`, `03_BACKLOG/`, `04_WORKFLOWS/`, `05_PROMPTS/`, `06_GOVERNANCE/`, `07_TEMPLATES/`, `08_SYNTHETIC_DEMOS/`, `09_HANDOFFS/`, `10_DECISION_LOG/`, `skills/`.
- **PM/Ops outcomes:** A coherent folder model that mirrors PM/Ops operating areas (planning, backlog, workflows, prompts, governance, templates, demos, handoffs, decisions).
- **AI integration relevance:** Establishes that AI is a workstream, not a side topic; sets the Gemini-first, platform-agnostic posture.
- **Safety and governance considerations:** Hard safety boundary stated in `README.md`, `MASTER_CONTEXT.md`, and `AI_GOVERNANCE_NOTES.md`; no employer data anywhere.
- **Completion criteria:** All scaffold folders and starter files exist with useful (not empty) starter content; handoff baseline is in place.
- **Dependencies and sequencing notes:** None.

### Phase 1 - Master Context and Continuity System

- **Purpose:** Make it possible for any future session, in either local-agent or chat-only mode, to resume cleanly without re-explaining the project.
- **Key files or artifact areas:** `00_MASTER_CONTEXT/MASTER_CONTEXT.md`, `09_HANDOFFS/SESSION_HANDOFF.md`, `09_HANDOFFS/SESSION_HANDOFF_TEMPLATE.md`, `10_DECISION_LOG/DECISION_LOG.md`, `skills/`.
- **PM/Ops outcomes:** Deterministic session-start and session-end protocols; explicit precedence rule between durable context and current status; a reusable handoff template that captures decisions, safety review, definition-of-done, AI tooling notes, and the next best prompt.
- **AI integration relevance:** Continuity protocol is usable by any chat-based AI (Gemini, Claude, OpenAI, Copilot) without leaking employer data, by requiring Tom to paste the source-of-truth files in chat-only mode.
- **Safety and governance considerations:** Session-end protocol is mode-gated for commits; chat-only mode never assumes filesystem access; safety boundary is restated at session start.
- **Completion criteria:** A new session can resume by reading `MASTER_CONTEXT.md`, `SESSION_HANDOFF.md`, and the named phase prompt, and finish by updating the handoff and decision log in the same session.
- **Dependencies and sequencing notes:** Phase 0 scaffold must exist.

### Phase 2 - Roadmap and Artifact Backlog

- **Purpose:** Turn the phase list into an actionable sequence and a prioritized backlog of templates, workflows, prompts, dashboards, checklists, and synthetic demos.
- **Key files or artifact areas:** `02_ROADMAP/ROADMAP.md` (this file), `03_BACKLOG/ARTIFACT_BACKLOG.md`, `01_MASTER_PLAN/MASTER_PLAN.md`.
- **PM/Ops outcomes:** A single place to see what is built, what is next, why each artifact exists, who uses it, what data it is safe to feed it, and what the human review point is.
- **AI integration relevance:** Backlog explicitly tags AI integration relevance, target environment assumption (Gemini-first), and data sensitivity posture per artifact, so future AI tooling discussions are concrete.
- **Safety and governance considerations:** No employer-specific dates, policies, programs, or internal deadlines. Every artifact is safe for synthetic or generic use unless explicitly approved later.
- **Completion criteria:** Roadmap covers all 13 phases with the required fields; backlog covers the required categories; cross-references are consistent across `MASTER_CONTEXT.md`, `MASTER_PLAN.md`, `ROADMAP.md`, and `ARTIFACT_BACKLOG.md`; `SESSION_HANDOFF.md` carries the Phase 3 next best prompt.
- **Dependencies and sequencing notes:** Phase 1 must be complete so the continuity loop can carry roadmap and backlog forward.

### Phase 3 - Governance and Tool Approval Strategy

- **Purpose:** Make AI integration credible and approval-friendly by codifying conservative governance, a tool approval intake, a data sensitivity decision model, a human-review and auditability model, and a safe conversation guide for AI discussions with management, IT, security, or compliance.
- **Key files or artifact areas:** `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`, optionally `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md`.
- **PM/Ops outcomes:** Tom can have a substantive AI integration conversation with a manager, security officer, or IT lead without overclaiming, without making policy assumptions, and without proposing shadow IT.
- **AI integration relevance:** Defines the conservative envelope inside which all later workflow, prompt, demo, and migration work must stay.
- **Safety and governance considerations:** Approved-tool-first, no shadow IT, human-in-the-loop, no sensitive data in personal tools; never claim knowledge of Motorola Solutions internal AI policy; never give legal advice.
- **Completion criteria:** A reader can use the governance bundle to (a) classify a candidate AI use case, (b) identify allowed data, (c) name the approved tool environment, (d) define a human review point, and (e) pilot safely with synthetic input.
- **Dependencies and sequencing notes:** Phase 2 backlog provides the catalog of artifacts that governance will gate.

### Phase 4 - Workflow Library

- **Purpose:** Build the manual-first PM/Ops workflow cards that ATLAS will refine and instrument over time.
- **Key files or artifact areas:** `04_WORKFLOWS/WORKFLOW_LIBRARY.md` and per-workflow Markdown files for reporting, action items, risk register, issue triage, schedule health, accounting reconciliation, lessons learned, and knowledge capture.
- **PM/Ops outcomes:** Repeatable, audit-friendly procedures Tom can run with or without AI assistance.
- **AI integration relevance:** Each workflow names where AI can help (drafting, summarizing, normalizing, comparing, sense-checking) and where a human must stay accountable (commitments, official statements, approvals).
- **Safety and governance considerations:** Workflows assume synthetic or sanitized inputs in personal mode; employer-deployable variants are flagged and held until governance approval is in place.
- **Completion criteria:** Every workflow has purpose, intended user, safe inputs, prohibited inputs, output format, AI assist point, human review point, and a portability note (Gemini-first, generalizable).
- **Dependencies and sequencing notes:** Phase 3 governance and the Phase 2 backlog define which workflows are in scope first.

### Phase 5 - Prompt Library

- **Purpose:** Build the Gemini-first prompt patterns that pair with the workflow library and remain portable to other approved AI tools.
- **Key files or artifact areas:** `05_PROMPTS/PROMPT_LIBRARY.md`, per-prompt Markdown files, prompt index.
- **PM/Ops outcomes:** Reliable prompts for status reporting, meeting-notes-to-actions, action aging, risk register cleanup, issue triage, schedule variance narrative, EVM variance support, reconciliation narrative, executive brief drafting, and lessons learned capture.
- **AI integration relevance:** Each prompt names its tool environment assumption, safe inputs, prohibited inputs, intended output, and human review point.
- **Safety and governance considerations:** Every prompt restates the safety boundary or inherits it from a referenced governance section; no prompt requires sensitive inputs.
- **Completion criteria:** Each workflow in Phase 4 has at least one paired prompt; prompts are usable without copying employer-internal context.
- **Dependencies and sequencing notes:** Phase 4 workflows define the prompt surface area; Phase 3 governance defines the data envelope.

### Phase 6 - First-Week Readiness Kit

- **Purpose:** Give Tom a conservative, high-leverage kit for clearance-limited onboarding.
- **Key files or artifact areas:** `07_TEMPLATES/FIRST_WEEK_DISCOVERY_SCRIPT.md`, `07_TEMPLATES/EXECUTIVE_NARRATIVE.md`, plus a listening plan, an onboarding question set, a clearance-limited value plan, and a "what I can offer this week" one-pager.
- **PM/Ops outcomes:** Tom can ask high-signal questions, listen well, document process gaps, propose conservative improvements, and signal AI fluency without overstepping.
- **AI integration relevance:** Kit identifies safe AI-assisted activities for week one (drafting notes from his own observations, summarizing public documents, organizing his own action list) and explicitly excludes employer data.
- **Safety and governance considerations:** No employer data, no real names, no internal program references, no calendar exports; all examples are Tom-authored or synthetic.
- **Completion criteria:** A reader can pick up the kit and run a credible discovery week without restricted access.
- **Dependencies and sequencing notes:** Phase 3 governance and Phase 5 prompts make the kit safe and useful.

### Phase 7 - Synthetic Demo Pack

- **Purpose:** Prove ATLAS workflow value with fictional data so Tom can demonstrate the operating system before real engagements.
- **Key files or artifact areas:** `08_SYNTHETIC_DEMOS/SYNTHETIC_STATUS_PACK_DEMO.md`, plus synthetic schedule variance, action tracker, risk register cleanup, and discrepancy triage demos.
- **PM/Ops outcomes:** A small bench of "before / after" demos showing how a workflow plus a prompt plus human review produces a cleaner artifact.
- **AI integration relevance:** Each demo shows the AI assist step explicitly and shows where the human reviewer changed the output.
- **Safety and governance considerations:** All inputs are fictional; demos carry a "synthetic data only" header; demos never imply employer endorsement.
- **Completion criteria:** Each demo has scenario, synthetic inputs, prompt used, raw AI output, human-reviewed output, and a one-paragraph value note.
- **Dependencies and sequencing notes:** Phases 4 and 5 must exist for demos to reference real workflow and prompt entries.

### Phase 8 - Microsoft Project and Schedule Integrity Track

- **Purpose:** Build schedule-health, variance-narrative, and cross-tool mismatch artifacts on synthetic schedules.
- **Key files or artifact areas:** `04_WORKFLOWS/` schedule entries, `07_TEMPLATES/` schedule narrative templates, `08_SYNTHETIC_DEMOS/` schedule scenarios.
- **PM/Ops outcomes:** Tom can review schedule integrity, summarize movement, and surface discrepancies without pretending to own technical estimates.
- **AI integration relevance:** AI assists with narrative drafting, anomaly summarization, and comparing exports; humans own dates, durations, and commitments.
- **Safety and governance considerations:** No real Microsoft Project files from employer systems; all `.mpp`-like inputs are synthetic CSV/Markdown stand-ins.
- **Completion criteria:** A schedule-health checklist, a variance narrative template, a cross-tool mismatch workflow, and at least one synthetic demo exist and reference each other.
- **Dependencies and sequencing notes:** Phases 4 and 5 supply the workflow and prompt shells.

### Phase 9 - EVM, Finance, and Project Accounting Track

- **Purpose:** Build EVM variance support, project accounting reconciliation, and accounting discrepancy artifacts on synthetic finance.
- **Key files or artifact areas:** `04_WORKFLOWS/` EVM and reconciliation entries, `07_TEMPLATES/` variance narrative templates, `08_SYNTHETIC_DEMOS/` finance scenarios.
- **PM/Ops outcomes:** Tom can draft variance explanations, walk reconciliation discrepancies, and propose follow-up questions without overclaiming financial authority.
- **AI integration relevance:** AI assists with narrative drafting, anomaly explanation, and structured comparison; humans own numbers, claims, and conclusions.
- **Safety and governance considerations:** No real accounting exports; all examples are synthetic and labeled.
- **Completion criteria:** EVM variance support prompt, project accounting reconciliation narrative template, accounting discrepancy workflow, and at least one synthetic demo exist and reference each other.
- **Dependencies and sequencing notes:** Phases 4 and 5 supply the workflow and prompt shells; Phase 8 informs cross-tool mismatch patterns.

### Phase 10 - SOP and Lessons Learned Track

- **Purpose:** Make repeatable PM/Ops knowledge a first-class output: SOP drafts and lessons learned capture.
- **Key files or artifact areas:** `04_WORKFLOWS/` SOP drafting and lessons learned entries, `07_TEMPLATES/` SOP and lessons learned templates, optional `04_WORKFLOWS/KNOWLEDGE_BASE_PATTERN.md`.
- **PM/Ops outcomes:** Tom can turn observed process into a reviewable draft SOP, and capture lessons learned while events are fresh.
- **AI integration relevance:** AI assists with first-draft structure, normalization, and tone; humans own approval and ownership.
- **Safety and governance considerations:** No real SOPs from employer systems; templates are generic.
- **Completion criteria:** SOP drafting workflow, lessons learned capture workflow, and at least one synthetic SOP and one synthetic lessons-learned example exist.
- **Dependencies and sequencing notes:** Phases 4 and 5 supply the workflow and prompt shells.

### Phase 11 - Employer Migration Plan

- **Purpose:** Define how approved workflows, prompts, templates, and demos can be safely migrated into employer-approved tools and environments.
- **Key files or artifact areas:** `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md` (if present from Phase 3), a new `11_EMPLOYER_MIGRATION/` area or top-level migration file once Phase 11 starts.
- **PM/Ops outcomes:** A migration playbook covering candidate selection, data path classification, approval intake, pilot, audit, and rollback.
- **AI integration relevance:** Defines where, when, and how ATLAS artifacts cross from personal preparation into employer-approved use.
- **Safety and governance considerations:** Migration assumes approval is granted in writing for each tool plus data path; never assumes blanket approval; never bypasses employer systems.
- **Completion criteria:** A migration playbook and per-artifact migration readiness checklist exist; the playbook explicitly avoids policy assumptions.
- **Dependencies and sequencing notes:** Deferred until the employer environment, policies, and approvals are known.

### Phase 12 - Final Operating System Review

- **Purpose:** Review ATLAS end-to-end against the safety boundary, Tom's PM/Ops value proposition, and migration readiness; produce a gap list, operating rhythm, and maintenance plan.
- **Key files or artifact areas:** A top-level `FINAL_REVIEW.md` (created in Phase 12), maintenance notes appended into existing files where relevant.
- **PM/Ops outcomes:** A concrete picture of what ATLAS is, what it is not, where it is strong, where it is weak, and what the next operating rhythm is.
- **AI integration relevance:** Review checks that AI usage stayed inside the conservative envelope set in Phase 3 and that no artifact silently drifted past it.
- **Safety and governance considerations:** Review verifies that no employer-sensitive material entered any file at any point.
- **Completion criteria:** Gap list, operating rhythm, and maintenance plan are written, agreed, and referenced from `MASTER_CONTEXT.md`.
- **Dependencies and sequencing notes:** Deferred until Phases 3 through 10 are complete and Phase 11 has at least a first draft.

## First three practical build moves (post-Phase 2)

1. **Phase 3 governance bundle.** Before writing more workflows, prompts, or demos, establish the conservative envelope that gates them.
2. **Phase 4 workflow shells.** Stand up workflow files for reporting, action items, risk register cleanup, issue triage, schedule health, accounting reconciliation, SOP drafting, and lessons learned, even if each is short.
3. **Phase 5 paired prompts.** Add at least one Gemini-first prompt per Phase 4 workflow so the operating system is usable end-to-end before demos and tracks deepen it.

## Decision gates

### Gate A - Pre-start safety gate

Before creating any demo, prompt, or workflow, confirm that all inputs are synthetic, public, generic, fictional, or Tom-authored non-proprietary material.

### Gate B - Employer-use gate

Before using any ATLAS artifact at work, confirm:

- The tool is approved for the data being used.
- The data is approved for that tool.
- The workflow does not bypass employer systems.
- A human remains responsible for review, approval, and official statements.
- No classified, CUI, ITAR/export-controlled, proprietary, customer, contract, schedule, finance, or technical data is placed into unapproved tools.

### Gate C - Automation gate

Before automating anything, confirm that the manual workflow is stable, understood, audit-friendly, and approved. ATLAS proves operating value before adding technical integrations.

### Gate D - Migration gate

Before migrating any ATLAS artifact into an employer-approved environment, confirm:

- A named human owner is accountable for the artifact in that environment.
- The data path is classified and approved.
- A rollback plan exists.
- Audit and retention expectations are met.

## Roadmap notes

ATLAS is built for durable PM/Ops leverage. The immediate aim is not to produce a large library; it is to produce a small set of reliable artifacts that help Tom listen well, ask strong questions, document process gaps, improve reporting quality, surface discrepancies, and propose responsible AI-enabled improvements in a conservative environment.

If onboarding clarifies that an assumed tool (Gemini Enterprise, Microsoft Project, Google Workspace) is not in use, the roadmap fields under "AI integration relevance" and "Safety and governance considerations" must be revised before downstream phases continue. The order of phases should stay the same unless a phase becomes irrelevant under the actual environment.
