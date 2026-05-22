# MASTER_CONTEXT.md

## Project identity

**Project name:** ATLAS PM/Ops OS  
**Meaning:** AI-enabled Tactical Learning, Automation, and Systems  
**Local target path:** `C:\Users\thalf\OneDrive\Documents\ATLAS-PM-Ops-OS`  
**Primary format:** Markdown-first local operating system  
**Current build stage:** Phase 1 - Master Context and Continuity System

ATLAS PM/Ops OS is a durable, local, repo-style operating system for project management, operations, project controls, and responsible AI workflow integration. It is not an app. It is not a database. It is not a deployment project. It is a structured body of working context, templates, workflows, prompts, governance notes, synthetic demos, and handoff files.

## User context

Tom Halfman, PMP has accepted a Project Manager / Operations Specialist role in Motorola Solutions Applied Technology in Schaumburg. The environment is federal/defense-adjacent and requires a U.S. security clearance. Until the clearance process is complete, access may be limited and Tom may be physically separated from cleared work areas.

Tom is not entering as the deepest RF engineer. His value proposition is PM/Ops and project-controls discipline combined with AI/ML fluency. He should position himself around project integrity, schedule and budget governance, EVM support, project accounting reconciliation, reporting quality, process compliance, discrepancy resolution, lessons learned, SOPs, dashboards, repeatable operating systems, and responsible AI workflow integration.

## AI value context

During the hiring process, the employer made clear that Tom's AI expertise is part of the expected value he brings. ATLAS should treat AI integration as a major workstream, not a side interest.

The goal is practical improvement, not hype. The system should identify and shape AI-enabled improvements that help with:

- Weekly status reporting
- Meeting notes to action items
- Action item aging and owner follow-up
- Microsoft Project schedule health review
- Schedule variance narratives
- EVM variance explanation support
- Risk register cleanup
- Issue and discrepancy triage
- Project accounting reconciliation narratives
- Lessons learned capture
- SOP draft generation
- Executive brief generation
- Cross-tool data mismatch investigation
- Google Drive, Docs, and Sheets knowledge workflows
- Clearance-limited onboarding workflows

## Known environment assumptions

These assumptions are working assumptions only. They must be validated after onboarding and adjusted when better information is available.

- Gemini Enterprise may be the only approved AI tool at first.
- Google Workspace is likely common.
- Microsoft Project is used.
- Excel and internal reporting systems are likely used.
- Claude, OpenAI, Codex, APIs, CLI tools, and MCP may not be approved at work initially.
- Employer approval, data handling rules, and security requirements override all personal preferences.

## Strict safety boundary

All pre-start and personal ATLAS work must use only:

- Synthetic data
- Public information
- Generic examples
- Fictional project scenarios
- Non-proprietary templates
- User-created fictional examples

ATLAS must never request, store, summarize, transform, or process the following in personal tools or unapproved systems:

- Classified data
- CUI
- ITAR or export-controlled data
- Proprietary employer data
- Customer data
- Contract data
- Internal schedules
- Internal financials
- Internal technical documents
- Nonpublic program names
- Real meeting notes
- Real project accounting exports
- Real employer Microsoft Project files
- Any employer data not explicitly approved for the specific tool and workflow

## Default operating posture

- Human-in-the-loop
- Audit-friendly
- Approved-tool-first
- Gemini-first and platform-agnostic
- No shadow IT
- No autonomous decisions
- No sensitive data in personal tools
- Clear separation between personal preparation and employer-deployable artifacts
- AI supports PM/Ops judgment; AI does not replace accountable human decision-making

## Source-of-truth hierarchy

When continuing ATLAS work, use the following source-of-truth order:

1. `00_MASTER_CONTEXT/MASTER_CONTEXT.md` for durable identity, constraints, positioning, and safety rules.
2. `09_HANDOFFS/SESSION_HANDOFF.md` for current status, most recent decisions, open items, and next best prompt.
3. `01_MASTER_PLAN/MASTER_PLAN.md` for phase structure and acceptance criteria.
4. `02_ROADMAP/ROADMAP.md` for milestone sequencing.
5. `03_BACKLOG/ARTIFACT_BACKLOG.md` for specific work items.
6. Governance, workflow, prompt, template, demo, decision, and skill files as needed.

If `MASTER_CONTEXT.md` and `SESSION_HANDOFF.md` disagree, treat `MASTER_CONTEXT.md` as authoritative for durable identity, scope, safety, and posture. Treat `SESSION_HANDOFF.md` as authoritative for current status, the most recent phase, and the next best prompt.

## Phase list (Phase 0 through Phase 12)

Phase content is detailed in `05_PROMPTS/PHASE_PROMPTS/` and tracked in `01_MASTER_PLAN/MASTER_PLAN.md` and `02_ROADMAP/ROADMAP.md`.

| Phase | Name | Purpose |
|---|---|---|
| 0 | Project Setup and Operating Rules | Establish the safe scaffold, operating rules, source-of-truth files, and starter artifacts. |
| 1 | Master Context and Continuity System | Harden durable context, session handoff process, and local skills so sessions continue cleanly and safely. |
| 2 | Roadmap and Artifact Backlog | Define milestone sequencing and the prioritized backlog of templates, workflows, prompts, dashboards, checklists, and demos. |
| 3 | Governance and Tool Approval Strategy | Capture AI governance posture, approval pathways, data boundaries, and risk controls. |
| 4 | Workflow Library | Build the library of manual-first PM/Ops workflows that can run with Gemini and remain portable. |
| 5 | Prompt Library | Build safe, Gemini-first prompt patterns that map to workflow steps and PM/Ops artifacts. |
| 6 | First-Week Readiness Kit | Assemble the conservative kit Tom uses during clearance-limited onboarding. |
| 7 | Synthetic Demo Pack | Build fictional demonstrations that prove ATLAS workflow value without real employer data. |
| 8 | Microsoft Project and Schedule Integrity Track | Build schedule-health, variance-narrative, and reporting-quality artifacts using synthetic schedules. |
| 9 | EVM, Finance, and Project Accounting Track | Build EVM support, project-accounting reconciliation, and variance-narrative artifacts using synthetic finance. |
| 10 | SOP and Lessons Learned Track | Build SOP drafting and lessons-learned capture workflows. |
| 11 | Employer Migration Plan | Define how approved workflows, prompts, and templates can be safely migrated to employer-approved tools. |
| 12 | Final Operating System Review | End-to-end review of ATLAS against the safety boundary, PM/Ops value proposition, and migration readiness. |

## Session-start protocol

Run this protocol at the beginning of every ATLAS work session, in both local-agent and chat-only modes.

1. Confirm the working directory: `C:\Users\thalf\OneDrive\Documents\ATLAS-PM-Ops-OS`.
2. Read `00_MASTER_CONTEXT/MASTER_CONTEXT.md`.
3. Read `09_HANDOFFS/SESSION_HANDOFF.md`.
4. Identify the current phase and the named next best prompt.
5. If the next best prompt points at a file in `05_PROMPTS/PHASE_PROMPTS/`, open and follow it.
6. Re-state the safety boundary in one line before producing any content.
7. State assumptions explicitly and proceed; ask only when genuinely blocked.

## Session-end protocol

Run this protocol at the end of every ATLAS work session that produced changes.

1. Update `09_HANDOFFS/SESSION_HANDOFF.md` using `09_HANDOFFS/SESSION_HANDOFF_TEMPLATE.md`.
2. Record: session date, current phase, session objective, files changed, completed work, decisions made, open items, risks, recommended next phase, and the next best prompt.
3. Complete the safety review checklist in the handoff.
4. If decisions were made, append them to `10_DECISION_LOG/DECISION_LOG.md`.
5. Confirm no employer-sensitive material entered any file or chat transcript.
6. Commit changes on a feature branch with a Conventional Commits message; never commit directly to `main`.

## Continuity protocol for local-agent vs chat-only usage

ATLAS must remain usable in two modes.

**Local-agent mode** (assistant has direct filesystem access to the repo):

- Read source-of-truth files directly from disk.
- Create or edit files in place under the working directory.
- Use feature branches; never edit `main` directly.
- Update `SESSION_HANDOFF.md` at the end of the session in-place.

**Chat-only mode** (assistant cannot reach the filesystem):

- Ask Tom to paste the contents of `MASTER_CONTEXT.md` and `SESSION_HANDOFF.md`.
- Produce full Markdown file contents or precise patch instructions with exact save paths.
- Do not assume any file write actually happened until Tom confirms.
- Produce the updated `SESSION_HANDOFF.md` content as a copy-paste block for Tom to save manually.

In both modes, do not invent file paths or employer-specific facts, and do not skip the safety boundary restatement.

## Definition of done for future sessions

A future ATLAS session is considered complete only when all of the following are true.

- The current phase and intent of the session are explicitly stated.
- Every produced artifact is safe under the hard safety boundary.
- Every produced artifact is Markdown-first and portable across Gemini, Google Workspace, Microsoft tools, and future approved systems.
- Every produced artifact has a clear purpose, intended user, safe inputs, prohibited inputs, and a human review step where relevant.
- `SESSION_HANDOFF.md` is updated with: date, phase, files changed, decisions, open items, safety review, and the next best prompt.
- Significant decisions are logged in `10_DECISION_LOG/DECISION_LOG.md`.
- No employer-sensitive material, real program names, real meeting notes, real schedules, or real financial data appear anywhere in the repo or transcript.
- No app, package dependency, API, database, deployment file, or code scaffolding was added unless the user explicitly requested it for that session.

## Artifact quality standards

Every ATLAS artifact should be:

- Safe for pre-start use
- Generic or synthetic unless explicitly approved otherwise
- Practical for PM/Ops execution
- Short enough to use under time pressure
- Structured enough to reuse
- Portable across Gemini, Google Workspace, Microsoft tools, and future approved systems
- Clear about assumptions, inputs, outputs, owners, and human approval points

## What ATLAS should avoid

- Building an app before there is a manual operating model
- Creating package dependencies, deployment files, databases, APIs, or code scaffolds without explicit instruction
- Inventing employer-specific facts
- Pretending to know internal processes before onboarding
- Using real employer data in personal tools
- Creating workflows that require shadow IT
- Allowing AI to make commitments, decisions, or official claims without human review

## Immediate objective

Phase 1 hardens the durable context, session handoff process, and continuity protocols so future ATLAS sessions can resume cleanly in either local-agent or chat-only mode without restarting. The next objective is Phase 2: Roadmap and Artifact Backlog, which will turn the phase list above into a sequenced milestone roadmap and a prioritized backlog of templates, workflows, prompts, and demos.
