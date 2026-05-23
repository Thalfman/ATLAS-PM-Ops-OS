# ARTIFACT_BACKLOG.md

## Backlog purpose

This backlog tracks every ATLAS artifact to build, refine, or migrate. It is the single ordered list that downstream phases pull from. The backlog stays practical and outcome-oriented. It does not include artifacts that require real employer data, unapproved tools, or speculative internal details.

The backlog is the input to Phase 3 (governance), Phase 4 (workflows), Phase 5 (prompts), Phase 6 (first-week kit), Phase 7 (synthetic demos), Phases 8 through 10 (specialized tracks), Phase 11 (migration), and Phase 12 (final review).

## Field definitions

Every backlog row uses the same field set:

- **ID** - stable identifier `A-XXXX`. IDs are append-only; never reused if an artifact is retired.
- **Artifact** - short name.
- **Category** - one of the standard categories listed below.
- **Phase** - target phase where the artifact is built.
- **Priority** - P0 through P3, defined in the priority key.
- **Purpose** - one sentence on what the artifact does for PM/Ops or AI integration.
- **Intended user** - who runs it (Tom personally, Tom in a meeting, a stakeholder, etc.).
- **Data sensitivity posture** - what data the artifact is safe with.
- **Target environment assumption** - the tool environment the artifact is designed for first.
- **Human review point** - where a human must sign off before the output is used.
- **Status** - from the status key.
- **Notes and dependencies** - sequencing, references, or open questions.

## Standard categories

- Continuity and project management
- Governance and tool approval
- Workflow library
- Prompt library
- First-week readiness
- Synthetic demos
- Microsoft Project and schedule integrity
- EVM, finance, and project accounting
- SOPs and lessons learned
- Employer migration
- Final review and maintenance

## Priority key

- **P0** - Needed for project continuity, safety, or governance.
- **P1** - High-value onboarding or early PM/Ops utility.
- **P2** - Useful once core operating patterns exist.
- **P3** - Later migration, automation, or enhancement.

## Status key

- **Seeded** - Starter version exists; needs hardening.
- **Hardened** - Phase 1+ pass complete; safe and reusable.
- **Not started** - No meaningful artifact yet.
- **Drafting** - Active build underway.
- **Ready for personal use** - Safe for Tom's preparation use.
- **Employer review needed** - Requires approval before workplace use.
- **Deferred** - Waiting for employer context or approval.

## Data sensitivity posture key

- **Synthetic-only** - Use only fictional or Tom-authored examples.
- **Public-or-synthetic** - Public, generic, or synthetic content allowed.
- **Tom-personal** - Tom's own notes and observations, not employer data.
- **Approved-employer** - Requires explicit employer approval; not used in personal mode.

## Target environment assumption key

- **Markdown-local** - Lives in this repo and is used in any text-capable tool.
- **Gemini-first** - Designed first for Gemini Enterprise inside Google Workspace; portable.
- **Workspace-doc** - Designed to live as a Google Doc, Sheet, or Slide under Google Workspace once approved.
- **Future-approved** - Lands in whatever employer-approved tool covers the workflow.

## Backlog

### Continuity and project management

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0001 | Master Context | Continuity and project management | 1 | P0 | Preserve project identity, safety boundaries, and role positioning across sessions. | Tom; any future ATLAS session. | Synthetic-only | Markdown-local | Tom confirms accuracy at session start. | Hardened | Lives at `00_MASTER_CONTEXT/MASTER_CONTEXT.md`. Updated in Phase 1. |
| A-0002 | Session Handoff System | Continuity and project management | 1 | P0 | Allow every session to resume without restarting. | Tom; any future ATLAS session. | Synthetic-only | Markdown-local | Tom reviews handoff at session end. | Hardened | Lives at `09_HANDOFFS/SESSION_HANDOFF.md` plus `SESSION_HANDOFF_TEMPLATE.md`. |
| A-0003 | Decision Log | Continuity and project management | 1 | P0 | Track assumptions, design choices, and rationale durably. | Tom. | Synthetic-only | Markdown-local | Tom signs off each entry as Active before close. | Hardened | Lives at `10_DECISION_LOG/DECISION_LOG.md`. Phase 1 added D-0006 through D-0013. |
| A-0026 | Roadmap | Continuity and project management | 2 | P0 | Sequence Phases 0 through 12 with purpose, outcomes, AI relevance, safety, completion criteria, and dependencies. | Tom; any future ATLAS session. | Synthetic-only | Markdown-local | Tom signs off the roadmap before Phase 3 begins. | Drafting | Lives at `02_ROADMAP/ROADMAP.md`. Phase 2 deliverable. |
| A-0027 | Artifact Backlog (this file) | Continuity and project management | 2 | P0 | Single ordered list of every ATLAS artifact with priority, status, safety posture, and human review point. | Tom; any future ATLAS session. | Synthetic-only | Markdown-local | Tom signs off backlog before Phase 3 begins. | Drafting | Phase 2 deliverable. |
| A-0028 | Master Plan alignment pass | Continuity and project management | 2 | P1 | Keep `MASTER_PLAN.md` aligned with the updated roadmap and backlog so source-of-truth files do not drift. | Tom; any future ATLAS session. | Synthetic-only | Markdown-local | Tom confirms alignment at end of Phase 2. | Drafting | Touch-up only. Avoid duplicating roadmap content into the plan. |
| A-0029 | Local skill files refresh | Continuity and project management | 4 | P2 | Update the three `skills/*/SKILL.md` files once Phase 4 workflow patterns are stable, so skill instructions match real workflow shape. | Tom. | Synthetic-only | Markdown-local | Tom reviews each skill file diff. | Not started | Held until Phase 4 stabilizes workflow patterns. |
| A-0030 | Phase prompt index maintenance | Continuity and project management | 2 | P1 | Keep `05_PROMPTS/PHASE_PROMPTS/PHASE_PROMPT_INDEX.md` aligned with the active phase set as roadmap evolves. | Tom; any future ATLAS session. | Synthetic-only | Markdown-local | Tom verifies index matches roadmap. | Seeded | Phase 2 confirms no changes needed; revisit if phases are added or removed. |

### Governance and tool approval

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0004 | AI Governance Notes | Governance and tool approval | 3 | P0 | Prevent unsafe AI use; support approval-friendly conversations. | Tom; managers, IT, security, compliance contacts. | Synthetic-only | Markdown-local | Tom reviews before sharing externally. | Hardened | Lives at `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`. Strengthened in Phase 3. |
| A-0021 | Employer Tool Approval Question Set | Governance and tool approval | 3 | P1 | Prepare credible questions for AI/tool governance conversations. | Tom in onboarding meetings. | Public-or-synthetic | Markdown-local | Tom adapts before any real conversation. | Hardened | Lives at `06_GOVERNANCE/EMPLOYER_TOOL_APPROVAL_QUESTION_SET.md`. |
| A-0031 | AI Tool Approval Strategy | Governance and tool approval | 3 | P0 | Define candidate-selection, data-path-classification, approved-tool, human-review, pilot, and documentation steps for AI use cases. | Tom. | Synthetic-only | Markdown-local | Tom signs off before any pilot. | Hardened | Lives at `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`. |
| A-0032 | Data Sensitivity Decision Model | Governance and tool approval | 3 | P0 | Classify a candidate input across categories (synthetic, public, Tom-personal, employer-approved, prohibited) and route it to a tool environment. | Tom. | Synthetic-only | Markdown-local | Tom uses model before each AI session. | Hardened | Lives at `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. |
| A-0033 | AI Conversation Guide | Governance and tool approval | 3 | P1 | Give Tom a safe pattern for talking about AI integration with management, IT, security, compliance, or program leadership. | Tom. | Public-or-synthetic | Markdown-local | Tom adapts before each conversation. | Hardened | Lives at `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md`. Does not assume employer policy. |
| A-0034 | Human Review and Auditability Model | Governance and tool approval | 3 | P0 | Define what a human review step looks like across reporting, schedule, finance, SOP, and lessons-learned outputs. | Tom. | Synthetic-only | Markdown-local | Tom signs off the model before Phase 4 builds workflows that reference it. | Hardened | Lives at `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`. Provides the "human review point" pattern reused across the backlog. |
| A-0035 | Prompt and Output Retention Note | Governance and tool approval | 3 | P1 | Capture conservative posture on prompt and output retention until employer policy is known. | Tom. | Public-or-synthetic | Markdown-local | Tom revisits after onboarding. | Hardened | Lives at `06_GOVERNANCE/PROMPT_AND_OUTPUT_RETENTION_NOTE.md`. |

### Workflow library

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0008 | Weekly Status Report Workflow | Workflow library | 4 | P1 | Improve consistency, traceability, and executive readability of weekly status. | Tom. | Synthetic-only | Gemini-first | Tom approves narrative before sharing. | Ready for personal use | Lives at `04_WORKFLOWS/W-01-weekly-status-report.md`. Pairs with executive narrative template and Phase 5 prompt A-0039. |
| A-0009 | Meeting Notes to Action Items Workflow | Workflow library | 4 | P1 | Convert discussion into owner/date/action structure. | Tom. | Tom-personal | Gemini-first | Tom confirms owner and date with attendees. | Ready for personal use | Lives at `04_WORKFLOWS/W-02-meeting-notes-to-actions.md`. Pairs with Phase 5 prompt A-0040. |
| A-0010 | Action Item Aging Workflow | Workflow library | 4 | P1 | Identify stale actions and prompt owner follow-up. | Tom. | Tom-personal | Gemini-first | Tom decides escalation. | Ready for personal use | Lives at `04_WORKFLOWS/W-03-action-item-aging.md`. Should not auto-message owners. Pairs with Phase 5 prompt A-0041. |
| A-0011 | Risk Register Cleanup Workflow | Workflow library | 4 | P1 | Clarify risk statements, triggers, mitigations, and owners. | Tom in a risk review meeting. | Synthetic-only | Gemini-first | Tom and risk owners approve cleaned entries. | Ready for personal use | Lives at `04_WORKFLOWS/W-07-risk-register-cleanup.md`. Pairs with Phase 5 prompt A-0042. |
| A-0012 | Issue and Discrepancy Triage Workflow | Workflow library | 4 | P1 | Convert ambiguous issues into trackable resolution paths. | Tom. | Synthetic-only | Gemini-first | Tom assigns owner and next step. | Ready for personal use | Lives at `04_WORKFLOWS/W-08-issue-and-discrepancy-triage.md`. Pairs with discrepancy triage demo A-0051 and Phase 5 prompt A-0043. |
| A-0020 | Google Workspace Knowledge Workflow | Workflow library | 4 | P2 | Improve findability and reuse in approved workspace tools. | Tom. | Public-or-synthetic | Workspace-doc | Tom verifies links and ownership before sharing. | Ready for personal use | Lives at `04_WORKFLOWS/W-14-google-workspace-knowledge.md`. Covers Drive, Docs, Sheets; assumes Workspace approval. |
| A-0036 | Schedule and Accounting Reconciliation Workflow | Workflow library | 4 | P1 | Walk a structured comparison between a schedule view and an accounting view to surface discrepancies. | Tom. | Synthetic-only | Gemini-first | Tom signs off discrepancy summary before sharing. | Ready for personal use | Lives at `04_WORKFLOWS/W-09-accounting-reconciliation-narrative.md`. Bridges Phases 8 and 9; pairs with cross-tool mismatch workflow (W-13) and Phase 5 prompt A-0019. |
| A-0037 | Cross-Tool Mismatch Workflow | Workflow library | 4 | P2 | Investigate discrepancies across schedule, status, and accounting views. | Tom. | Synthetic-only | Gemini-first | Tom signs off findings. | Ready for personal use | Lives at `04_WORKFLOWS/W-13-cross-tool-mismatch-investigation.md`. Was A-0017 in the seeded backlog; renamed and re-anchored here. |
| A-0038 | Process Gap Note Workflow | Workflow library | 4 | P1 | Capture an observed process gap as a short, neutral, ownership-aware note suitable for raising with a manager. | Tom. | Tom-personal | Markdown-local | Tom decides whether and how to raise the note. | Not started | High leverage during clearance-limited onboarding. Deferred to a follow-up Phase 4 session; not in the Phase 4 prompt's minimum 15. |
| A-0066 | EVM Variance Explanation Support Workflow | Workflow library | 4 | P2 | Structure cause-impact-corrective-action narratives for EVM variance without overclaiming. | Tom. | Synthetic-only | Gemini-first | Tom and finance/program controls reviewer approve before sharing. | Ready for personal use | Lives at `04_WORKFLOWS/W-06-evm-variance-explanation.md`. Bridges Phases 4 and 9; pairs with synthetic EVM workbook A-0054 and Phase 5 prompt A-0018. Added in Phase 4 per D-0032. |
| A-0067 | Executive Brief Generation Workflow | Workflow library | 4 | P1 | Compress program state into a leadership-ready brief without overclaiming. | Tom. | Synthetic-only | Gemini-first | Tom approves; program lead approves any employer-deployable brief. | Ready for personal use | Lives at `04_WORKFLOWS/W-12-executive-brief-generation.md`. Pairs with `07_TEMPLATES/EXECUTIVE_NARRATIVE.md` and Phase 5 prompt A-0044. Added in Phase 4 per D-0032. |
| A-0068 | Clearance-Limited Onboarding Workflow | Workflow library | 4 | P1 | Demonstrate observable PM/Ops and AI value during clearance-limited onboarding without touching restricted content. | Tom; manager. | Tom-personal | Markdown-local | Manager approves the week's commitments and any shared "what I can offer" framing. | Ready for personal use | Lives at `04_WORKFLOWS/W-15-clearance-limited-onboarding.md`. Pairs with A-0022, A-0048, A-0050, A-0049, A-0005, A-0006. Added in Phase 4 per D-0032. |

### Prompt library

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0039 | Weekly Status Drafting Prompt | Prompt library | 5 | P1 | Draft a weekly status update from Tom's own notes. | Tom. | Tom-personal | Gemini-first | Tom edits and approves before sharing. | Ready for personal use | Lives at `05_PROMPTS/P-01-weekly-status-drafting.md`. Pairs with W-01 / A-0008. |
| A-0040 | Meeting Notes to Actions Prompt | Prompt library | 5 | P1 | Convert raw notes into owner/date/action lines. | Tom. | Tom-personal | Gemini-first | Tom verifies owner and date. | Ready for personal use | Lives at `05_PROMPTS/P-02-meeting-notes-to-actions.md`. Pairs with W-02 / A-0009. |
| A-0041 | Action Aging Summary Prompt | Prompt library | 5 | P1 | Summarize aging actions and propose follow-up framing. | Tom. | Tom-personal | Gemini-first | Tom approves any follow-up messages. | Ready for personal use | Lives at `05_PROMPTS/P-03-action-aging-summary.md`. Pairs with W-03 / A-0010. |
| A-0042 | Risk Register Cleanup Prompt | Prompt library | 5 | P1 | Normalize risk statements into a consistent format. | Tom. | Synthetic-only | Gemini-first | Tom and risk owners approve. | Ready for personal use | Lives at `05_PROMPTS/P-07-risk-register-cleanup.md`. Pairs with W-07 / A-0011. |
| A-0043 | Issue and Discrepancy Triage Prompt | Prompt library | 5 | P1 | Structure ambiguous issues into clear triage entries. | Tom. | Synthetic-only | Gemini-first | Tom assigns owner and next step. | Ready for personal use | Lives at `05_PROMPTS/P-08-issue-and-discrepancy-triage.md`. Pairs with W-08 / A-0012. |
| A-0018 | EVM Variance Explanation Support Prompt | Prompt library | 5 | P2 | Help draft human-reviewed variance explanations from synthetic EVM data. | Tom. | Synthetic-only | Gemini-first | Tom and accountable owner approve before sharing. | Ready for personal use | Lives at `05_PROMPTS/P-06-evm-variance-explanation.md`. Pairs with W-06 / A-0066. Bridges Phases 5 and 9. |
| A-0019 | Project Accounting Reconciliation Narrative Template | Prompt library | 5 | P2 | Explain reconciliation discrepancies without overclaiming. | Tom. | Synthetic-only | Gemini-first | Tom and accounting reviewer approve. | Ready for personal use | Lives at `05_PROMPTS/P-09-accounting-reconciliation-narrative.md`. Pairs with W-09 / A-0036. Bridges Phases 5 and 9. |
| A-0044 | Executive Brief Drafting Prompt | Prompt library | 5 | P1 | Compress weekly status or program state into a leadership-ready brief. | Tom. | Synthetic-only | Gemini-first | Tom approves before sharing. | Ready for personal use | Lives at `05_PROMPTS/P-12-executive-brief-drafting.md`. Pairs with W-12 / A-0067 and `07_TEMPLATES/EXECUTIVE_NARRATIVE.md`. |
| A-0045 | SOP First Draft Prompt | Prompt library | 5 | P2 | Generate a first-draft SOP from observed steps. | Tom. | Synthetic-only | Gemini-first | Tom and SOP owner approve. | Ready for personal use | Lives at `05_PROMPTS/P-11-sop-first-draft.md`. Pairs with W-11 / A-0014 (SOP Draft Generation Workflow). |
| A-0046 | Lessons Learned Capture Prompt | Prompt library | 5 | P2 | Convert raw event notes into structured lessons learned entries. | Tom. | Synthetic-only | Gemini-first | Tom and project leadership approve. | Ready for personal use | Lives at `05_PROMPTS/P-10-lessons-learned-capture.md`. Pairs with W-10 / A-0013. |
| A-0047 | Schedule Variance Narrative Prompt | Prompt library | 5 | P1 | Draft a schedule variance narrative from synthetic schedule deltas. | Tom. | Synthetic-only | Gemini-first | Tom and schedule owner approve. | Ready for personal use | Lives at `05_PROMPTS/P-05-schedule-variance-narrative.md`. Pairs with W-05 / A-0016. |

### First-week readiness

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0005 | First-Week Discovery Script | First-week readiness | 6 | P1 | Help Tom ask useful questions without restricted access. | Tom in week one. | Public-or-synthetic | Markdown-local | Tom adapts before each meeting. | Ready for personal use | Lives at `07_TEMPLATES/FIRST_WEEK_DISCOVERY_SCRIPT.md`. Hardened in Phase 6 with governance envelope, W-15 reference, first-manager-1:1 questions, knowledge-management/Workspace questions, things-not-to-do list, and end-of-week summary template. Indexed in `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`. |
| A-0006 | Executive Narrative Template | First-week readiness | 6 | P1 | Produce concise PM/Ops updates and leadership-ready summaries. | Tom. | Synthetic-only | Markdown-local | Tom approves before sharing. | Ready for personal use | Lives at `07_TEMPLATES/EXECUTIVE_NARRATIVE.md`. Hardened in Phase 6 with governance envelope, PM/Ops + AI positioning paragraph, forward-looking marker, reviewer sign-off line, failure modes, and migration notes. Pairs with W-12 / P-12. Indexed in `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`. |
| A-0022 | Clearance-Limited Value Plan | First-week readiness | 6 | P1 | Identify valuable work Tom can do without restricted access. | Tom. | Tom-personal | Markdown-local | Tom signs off before discussing with manager. | Ready for personal use | Lives at `07_TEMPLATES/CLEARANCE_LIMITED_VALUE_PLAN.md`. Eight value categories with visible-artifact discipline. Pairs with `WHAT_I_CAN_OFFER_THIS_WEEK.md` for the manager-shared one-pager. Indexed in `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`. |
| A-0048 | Listening Plan | First-week readiness | 6 | P1 | Structure how Tom listens for process gaps, reporting issues, and AI-adjacent pain points. | Tom. | Tom-personal | Markdown-local | Tom reviews end of each day. | Ready for personal use | Lives at `07_TEMPLATES/LISTENING_PLAN.md`. Daily-entry shape, sanitization filter, Friday reflection. Pairs with future `04_WORKFLOWS/W-16-process-gap-note.md` (A-0038). Indexed in `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`. |
| A-0049 | Onboarding Question Set | First-week readiness | 6 | P1 | A safe question bank for managers, peers, IT, security, and program contacts. | Tom. | Public-or-synthetic | Markdown-local | Tom adapts before each conversation. | Ready for personal use | Lives at `07_TEMPLATES/ONBOARDING_QUESTION_SET.md`. Six audience-split banks (manager, peers, IT, security, compliance, program leadership) with venue/rapport/clearance markers. Cross-references `06_GOVERNANCE/EMPLOYER_TOOL_APPROVAL_QUESTION_SET.md`. Indexed in `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`. |
| A-0050 | "What I Can Offer This Week" One-Pager | First-week readiness | 6 | P1 | Communicate Tom's PM/Ops and AI value during clearance-limited onboarding without overclaiming. | Tom; manager. | Tom-personal | Markdown-local | Tom edits and signs off before sharing. | Ready for personal use | Lives at `07_TEMPLATES/WHAT_I_CAN_OFFER_THIS_WEEK.md`. Manager-shared expression of the A-0022 menu, with do-not-promise list, drafting checklist, and W-15-aligned red flags. Scope rule logged as D-0044. Indexed in `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`. |

### Synthetic demos

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0007 | Synthetic Status Pack Demo | Synthetic demos | 7 | P1 | Demonstrate AI-assisted reporting value with fictional data. | Tom; demo audience. | Synthetic-only | Markdown-local | Tom presents only as a synthetic demo. | Ready for personal use | Lives at `08_SYNTHETIC_DEMOS/SYNTHETIC_STATUS_PACK_DEMO.md`. Hardened in Phase 7 with paired W-01 / W-12, paired P-01 / P-12, shared scenario reference, and the "Status and reporting outputs" review pattern. Indexed in `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`. |
| A-0023 | Synthetic Schedule Variance Demo | Synthetic demos | 7 | P2 | Show schedule analysis value using fictional schedule data. | Tom; demo audience. | Synthetic-only | Markdown-local | Tom presents only as a synthetic demo. | Ready for personal use | Lives at `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md`. Pairs with W-05 / P-05; "Schedule outputs" review pattern. Cross-references A-0016 (Phase 8 schedule track). Indexed in `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`. |
| A-0024 | Synthetic Action Tracker Demo | Synthetic demos | 7 | P2 | Show owner/date/action hygiene value using fictional action data. | Tom; demo audience. | Synthetic-only | Markdown-local | Tom presents only as a synthetic demo. | Ready for personal use | Lives at `08_SYNTHETIC_DEMOS/SYNTHETIC_ACTION_TRACKER_DEMO.md`. Two halves: extraction (W-02 / P-02) and aging (W-03 / P-03); "Meeting notes to action items" review pattern. Indexed in `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`. |
| A-0051 | Synthetic Discrepancy Triage Demo | Synthetic demos | 7 | P2 | Show issue/discrepancy triage value using fictional data. | Tom; demo audience. | Synthetic-only | Markdown-local | Tom presents only as a synthetic demo. | Ready for personal use | Lives at `08_SYNTHETIC_DEMOS/SYNTHETIC_DISCREPANCY_TRIAGE_DEMO.md`. Pairs with W-08 / P-08; "Risk and issue triage outputs" review pattern. AI proposes investigation candidates; Tom assigns severity and owner. Indexed in `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`. |
| A-0052 | Synthetic Risk Register Cleanup Demo | Synthetic demos | 7 | P2 | Show risk register cleanup value using fictional data. | Tom; demo audience. | Synthetic-only | Markdown-local | Tom presents only as a synthetic demo. | Ready for personal use | Lives at `08_SYNTHETIC_DEMOS/SYNTHETIC_RISK_REGISTER_CLEANUP_DEMO.md`. Pairs with W-07 / P-07; "Risk and issue triage outputs" review pattern. AI flags vague entries and merge candidates; owners decide probability/impact/response. Indexed in `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`. |

### Microsoft Project and schedule integrity

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0015 | Microsoft Project Schedule Health Checklist | Microsoft Project and schedule integrity | 8 | P1 | Review schedule integrity without owning technical estimates. | Tom. | Synthetic-only | Markdown-local | Tom and schedule owner agree on findings. | Ready for personal use | Lives at `07_TEMPLATES/SCHEDULE_HEALTH_REVIEW_TEMPLATE.md`. Generic A..L checklist plus Microsoft Project data-handling note (per D-0051). Pairs with W-04 / A-0053 workbook. |
| A-0016 | Schedule Variance Narrative Template | Microsoft Project and schedule integrity | 8 | P1 | Convert schedule movement into clear PM/Ops explanations. | Tom. | Synthetic-only | Markdown-local | Tom and schedule owner approve. | Ready for personal use | Lives at `07_TEMPLATES/SCHEDULE_VARIANCE_NARRATIVE_TEMPLATE.md`. Pairs with W-05 / P-05 / A-0047 prompt and the Phase 7 schedule variance demo (A-0023). Includes a number-trace appendix and forward-looking marker. |
| A-0053 | Synthetic Schedule Workbook | Microsoft Project and schedule integrity | 8 | P2 | A fictional schedule (Markdown/CSV) that demos and checklists can reference safely. | Tom. | Synthetic-only | Markdown-local | Tom curates and labels as synthetic. | Ready for personal use | Lives at `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_WORKBOOK.md`. 24-task fictional schedule on Project Northstar Demo with critical path, slack, constraints; supports the Phase 8 templates and extends the Phase 7 variance demo. No real `.mpp` files produced or referenced. |

### EVM, finance, and project accounting

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0054 | Synthetic EVM Workbook | EVM, finance, and project accounting | 9 | P2 | A fictional EVM dataset (BCWS/BCWP/ACWP, CV, SV) for prompts and demos. | Tom. | Synthetic-only | Markdown-local | Tom labels as synthetic. | Ready for personal use | Lives at `08_SYNTHETIC_DEMOS/SYNTHETIC_EVM_WORKBOOK.md`. Three control accounts (CA-A/B/C) on Project Northstar Demo, BCWS/BCWP/ACWP/CV/SV/CPI/SPI at week-3 cutoff, illustrative EAC. Pairs with W-06 / P-06 / A-0018; cross-references Phase 8 schedule workbook for cause cross-walk. |
| A-0055 | Project Accounting Reconciliation Walkthrough | EVM, finance, and project accounting | 9 | P2 | Step-by-step walkthrough of a fictional reconciliation discrepancy. | Tom. | Synthetic-only | Markdown-local | Tom and accounting reviewer approve. | Ready for personal use | Lives at `08_SYNTHETIC_DEMOS/SYNTHETIC_ACCOUNTING_RECONCILIATION_DEMO.md`. Four-view reconciliation (EVM ACWP / ledger / time-tracking / status pack narrative), 50-unit spread, AI proposes drivers and investigation questions without asserting cause. Pairs with W-09 / P-09 / A-0019. |
| A-0056 | Accounting Discrepancy Triage Workflow | EVM, finance, and project accounting | 9 | P2 | Structured way to surface and route accounting discrepancies without overclaiming. | Tom. | Synthetic-only | Markdown-local | Tom and accounting reviewer approve. | Ready for personal use | Lives at `04_WORKFLOWS/W-17-accounting-discrepancy-triage.md` (new W-NN, sibling to W-08 issue triage and W-13 cross-tool mismatch). 16-section workflow card conforming to D-0029 schema. Triage record feeds the next W-09 reconciliation narrative. |

### SOPs and lessons learned

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0013 | Lessons Learned Capture Workflow | SOPs and lessons learned | 10 | P1 | Capture repeatable learning while events are fresh. | Tom; project team. | Synthetic-only | Gemini-first | Tom and project leadership approve before publication. | Ready for personal use | Workflow lives at `04_WORKFLOWS/W-10-lessons-learned-capture.md` (Phase 4); template lives at `07_TEMPLATES/LESSONS_LEARNED_TEMPLATE.md` (A-0058, Phase 10). Pairs with A-0046 prompt and the W-10 card; the Phase 10 template is the fillable companion. |
| A-0014 | SOP Draft Generation Workflow | SOPs and lessons learned | 10 | P1 | Turn observed process into reviewable draft SOPs. | Tom; process owner. | Synthetic-only | Gemini-first | Process owner approves before publication. | Ready for personal use | Workflow lives at `04_WORKFLOWS/W-11-sop-draft-generation.md` (Phase 4); template lives at `07_TEMPLATES/SOP_TEMPLATE.md` (A-0057, Phase 10). Pairs with A-0045 prompt and the W-11 card; the Phase 10 template is the fillable companion. |
| A-0057 | SOP Template | SOPs and lessons learned | 10 | P2 | Generic SOP shape (purpose, scope, inputs, steps, controls, owner, review cadence). | Tom; process owner. | Synthetic-only | Markdown-local | Process owner approves. | Ready for personal use | Lives at `07_TEMPLATES/SOP_TEMPLATE.md`. 10-section fillable SOP shape with role-owner discipline, testable-step requirement, controls section, revision history, approval line. Pairs with A-0014 / W-11 / P-11. |
| A-0058 | Lessons Learned Template | SOPs and lessons learned | 10 | P2 | Generic lessons learned shape (event, what happened, what we expected, gap, recommendation, owner). | Tom; project leadership. | Synthetic-only | Markdown-local | Project leadership approves. | Ready for personal use | Lives at `07_TEMPLATES/LESSONS_LEARNED_TEMPLATE.md`. Fillable shape framed at process / information-flow / tool level (never individual blame). Pairs with A-0013 / W-10 / P-10. |
| A-0059 | Knowledge Base Pattern | SOPs and lessons learned | 10 | P3 | Generic pattern for organizing SOPs and lessons learned for findability and reuse. | Tom. | Synthetic-only | Workspace-doc | Tom and knowledge owner approve before deploying. | Ready for personal use | Lives at `07_TEMPLATES/KNOWLEDGE_BASE_PATTERN.md`. Six-element pattern (naming and addressing, metadata, findability, reuse over copy, review cadence, retirement). Tool-agnostic; ATLAS itself instantiates the pattern via the library / pack / kit indexes. |

### Employer migration

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0025 | Employer Migration Plan | Employer migration | 11 | P3 | Convert local artifacts into approved workplace workflows after validation. | Tom; manager; IT and security contacts. | Approved-employer | Future-approved | Approval required per artifact before migration. | Deferred | Depends on actual environment and approvals. |
| A-0060 | Per-Artifact Migration Readiness Checklist | Employer migration | 11 | P3 | A short checklist applied to each ATLAS artifact before migration. | Tom. | Approved-employer | Markdown-local | Tom signs off per artifact; relevant employer approver signs off in writing. | Deferred | Pairs with A-0025. |
| A-0061 | Migration Rollback Note | Employer migration | 11 | P3 | Capture rollback steps for any migrated artifact. | Tom. | Approved-employer | Markdown-local | Tom and accountable employer owner approve. | Deferred | Pairs with A-0025. |

### Final review and maintenance

| ID | Artifact | Category | Phase | Priority | Purpose | Intended user | Data sensitivity posture | Target environment assumption | Human review point | Status | Notes and dependencies |
|---|---|---|---:|---|---|---|---|---|---|---|---|
| A-0062 | Final Operating System Review | Final review and maintenance | 12 | P3 | End-to-end review of ATLAS against safety boundary, value proposition, and migration readiness. | Tom. | Synthetic-only | Markdown-local | Tom signs off before resetting operating rhythm. | Deferred | Phase 12. |
| A-0063 | Gap List | Final review and maintenance | 12 | P3 | Capture what is missing, weak, or stale across the operating system. | Tom. | Synthetic-only | Markdown-local | Tom prioritizes gaps before next operating cycle. | Deferred | Pairs with A-0062. |
| A-0064 | Operating Rhythm | Final review and maintenance | 12 | P3 | Define the steady-state cadence for using and maintaining ATLAS. | Tom. | Synthetic-only | Markdown-local | Tom commits to the cadence; revisits monthly. | Deferred | Pairs with A-0062. |
| A-0065 | Maintenance Plan | Final review and maintenance | 12 | P3 | Define how ATLAS gets refreshed, retired, or migrated over time. | Tom. | Synthetic-only | Markdown-local | Tom owns the plan; revisits at major transitions. | Deferred | Pairs with A-0062. |

## Current build recommendation

Phases 1 through 10 are complete. Phase 10 (SOP and Lessons Learned Track) is `Ready for personal use` for all five backlog rows: A-0013 Lessons Learned Capture Workflow (workflow at W-10; template at `LESSONS_LEARNED_TEMPLATE.md`), A-0014 SOP Draft Generation Workflow (workflow at W-11; template at `SOP_TEMPLATE.md`), A-0057 SOP Template (`07_TEMPLATES/SOP_TEMPLATE.md`), A-0058 Lessons Learned Template (`07_TEMPLATES/LESSONS_LEARNED_TEMPLATE.md`), and A-0059 Knowledge Base Pattern (`07_TEMPLATES/KNOWLEDGE_BASE_PATTERN.md`). Phase 10 adds the three new templates under `07_TEMPLATES/`; the two workflow rows (A-0013, A-0014) are flipped because the Phase 4 W-10 / W-11 cards plus the new Phase 10 templates together satisfy the "workflow" deliverable definition (workflow card publishes the process; template publishes the fillable shape). No new W-NN or P-NN added in Phase 10.

Phase 11 (Employer Migration Plan) is next: define how approved workflows, prompts, and templates can be safely migrated to employer-approved tools. Backlog rows for Phase 11 are A-0025 (Employer Migration Plan), A-0060 (Per-Artifact Migration Readiness Checklist), and A-0061 (Migration Rollback Note) — all currently `Deferred` pending actual environment and approvals; Phase 11 promotes them to `Ready for personal use` as conservative personal-preparation versions while keeping the deferred-until-real-approvals discipline. Optional housekeeping during or after Phase 11: build A-0038 Process Gap Note as `04_WORKFLOWS/W-16-process-gap-note.md`, and refresh A-0029 local skill files against the now-stable Phase 4 / 5 / 6 / 7 / 8 / 9 / 10 patterns.

## Backlog hygiene rules

- **Append-only IDs.** Retire artifacts by changing status to `Deferred` or by writing a "Retired - see A-NNNN" row; never reuse an ID.
- **One sentence per field.** Backlog rows are for orientation, not specifications. The artifact itself lives in its phase folder.
- **Source-of-truth pointer.** Each artifact named here ends up in a Markdown file under the matching phase folder; the backlog row points at that file once it exists.
- **No employer data, ever.** Backlog rows must not reference real program names, real schedules, real finance numbers, or real contract data.
- **Update with decisions.** When a decision changes priority, status, or scope, log it in `10_DECISION_LOG/DECISION_LOG.md` and reflect it here in the same session.
