# FIRST_WEEK_READINESS_KIT.md

## Kit identity

- **Phase:** 6 - First-Week Readiness Kit
- **Operating workflow:** `04_WORKFLOWS/W-15-clearance-limited-onboarding.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

The First-Week Readiness Kit is the conservative set of personal-preparation artifacts Tom uses during clearance-limited onboarding. It helps Tom listen first, ask the right questions, demonstrate observable PM/Ops and AI value without restricted access, and commit to the manager only what Tom can deliver inside the safety boundary.

Phase 6 inherits the Phase 3 governance envelope and references W-15 as the operating workflow. The kit lives under `07_TEMPLATES/`. This file is the index; each sub-file is a small, focused artifact.

## Governance envelope (applies to all kit files)

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Tom-personal by default. Public when based on public material. Synthetic when refining ATLAS demo content. Never Employer-approved while clearance is pending.
- **Tool environment** (same file, "Tool environments"): ATLAS-local Markdown for templates and generic-enough entries. Personal AI tool acceptable on Synthetic / Public / Tom-personal inputs only. Tom-personal notes (outside ATLAS) for anything that would be hard to fully sanitize.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Light for personal practice; Standard for any artifact shared with the manager (notably `WHAT_I_CAN_OFFER_THIS_WEEK.md`).
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Status and reporting outputs.

Sub-files cite this envelope by filename in their own headers. Per D-0042, the envelope is not restated at the kit-artifact layer.

## Use posture

- Listen first; propose second.
- Bring 3-5 commitments to each manager 1:1, not a wishlist.
- Every commitment names a visible artifact and a target date.
- Capture observations in neutral, generic language; nothing in ATLAS that could be read as paraphrased restricted content.
- AI in personal preparation only, on synthetic or public material, with named human review on every output.
- Do not promise outcomes that depend on cleared access or on approvals that do not yet exist.

## Kit index

| File | Backlog A-ID | Purpose | Default review intensity |
|---|---|---|---|
| `FIRST_WEEK_DISCOVERY_SCRIPT.md` | A-0005 | General question script Tom adapts before each meeting. | Light |
| `EXECUTIVE_NARRATIVE.md` | A-0006 | Synthetic-practice template for leadership-ready narratives; pairs with W-12 / P-12. | Standard |
| `CLEARANCE_LIMITED_VALUE_PLAN.md` | A-0022 | Menu of value Tom can deliver without restricted access. | Light |
| `LISTENING_PLAN.md` | A-0048 | Daily-cadence structure for observation capture in neutral language. | Light |
| `ONBOARDING_QUESTION_SET.md` | A-0049 | Audience-split safe question banks (manager, peers, IT, security, compliance, program leadership). | Light |
| `WHAT_I_CAN_OFFER_THIS_WEEK.md` | A-0050 | One-pager template Tom shares with the manager each week. | Standard |
| `AI_INTEGRATION_DISCUSSION_GUIDE.md` | (utility, D-0043) | Conservative talking points for early AI integration conversations. | Light |

All sub-files live in `07_TEMPLATES/` alongside this index. The utility-template entry mirrors the P-00 / P-99 pattern in `05_PROMPTS/PROMPT_LIBRARY.md` (D-0038): tracked here, not in the backlog.

## Universal kit rules

1. Run a one-line sanity check before drafting any kit-output instance: data category, tool environment, review intensity, named human reviewer.
2. Use placeholders for any specific people, programs, customers, or numbers. The placeholder set in the discovery script and the one-pager template is canonical.
3. Forbid invention. If Tom does not know a name, role, cadence, or process, mark it as a question for the manager - do not guess.
4. Capture observations in generic language. If an entry cannot be written without restricted content, do not write it.
5. Keep a named human reviewer. For manager-shared artifacts, the manager is the accountable approver of scope; Tom is the accountable author of the draft.
6. Cite, do not redefine. Each sub-file cites the Phase 3 governance bundle and W-15 by filename. No policy re-litigation at the kit layer.

## 14 content buckets named by the Phase 6 prompt (where each lives)

The Phase 6 prompt lists 14 buckets the first-week kit should include. The kit covers each by routing it to the right sub-file. None are restated here.

| Bucket from the phase prompt | Where it lives |
|---|---|
| First-week goals | `WHAT_I_CAN_OFFER_THIS_WEEK.md` (commitments and scope) |
| First manager 1:1 questions | `ONBOARDING_QUESTION_SET.md` §A (Manager) and `FIRST_WEEK_DISCOVERY_SCRIPT.md` (Role and success criteria) |
| Stakeholder listening-tour questions | `ONBOARDING_QUESTION_SET.md` §B (Peers) and §F (Program leadership) |
| PM/Ops process discovery questions | `FIRST_WEEK_DISCOVERY_SCRIPT.md` (Role and success criteria; Reporting and communication) |
| Reporting and cadence discovery questions | `FIRST_WEEK_DISCOVERY_SCRIPT.md` (Reporting and communication) |
| Schedule and Microsoft Project discovery questions | `FIRST_WEEK_DISCOVERY_SCRIPT.md` (Schedule and Microsoft Project) |
| Finance/EVM/accounting discovery questions | `FIRST_WEEK_DISCOVERY_SCRIPT.md` (Finance, EVM, and project accounting) |
| Risk/issue/action tracking discovery questions | `FIRST_WEEK_DISCOVERY_SCRIPT.md` (Risk, issue, and discrepancy) |
| Knowledge management / Google Workspace discovery questions | `FIRST_WEEK_DISCOVERY_SCRIPT.md` (Knowledge management and Workspace) |
| AI/tool approval discovery questions | `FIRST_WEEK_DISCOVERY_SCRIPT.md` (AI workflow discovery) and `ONBOARDING_QUESTION_SET.md` §C (IT) / §D (Security) / §E (Compliance) |
| Clearance-limited contribution options | `CLEARANCE_LIMITED_VALUE_PLAN.md` (eight value categories) |
| How to frame AI integration responsibly | `AI_INTEGRATION_DISCUSSION_GUIDE.md` (Tom's framing; talking points by audience) |
| Things not to do in week one | `FIRST_WEEK_DISCOVERY_SCRIPT.md` (Things not to do in week one) and `AI_INTEGRATION_DISCUSSION_GUIDE.md` (Hard "do not" list) |
| End-of-week summary template | `FIRST_WEEK_DISCOVERY_SCRIPT.md` (End-of-week summary) and `LISTENING_PLAN.md` (Weekly reflection) |

## Maintenance and decision log

- Kit sub-file IDs follow the existing backlog A-IDs; append-only per D-0017.
- Schema changes (the governance envelope shape, the "Used by" block, the cross-references shape) apply to all sub-files. Update this index first, then back-port every sub-file in the same session, then log the change.
- Future kit additions for follow-on phases (e.g., after-clearance variations) get their own A-IDs and rows in the backlog; do not retire existing kit files in place.
- Edits that would weaken the safety boundary (e.g., loosening the do-not-promise list, blurring synthetic vs employer data) require a new logged decision before being accepted.

## Cross-references

- Operating workflow: `04_WORKFLOWS/W-15-clearance-limited-onboarding.md`.
- Workflow library index: `04_WORKFLOWS/WORKFLOW_LIBRARY.md`.
- Prompt library index: `05_PROMPTS/PROMPT_LIBRARY.md` (paired prompts cited by kit files: P-12 executive brief drafting; P-11 SOP first draft used in synthetic practice).
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`, `AI_CONVERSATION_GUIDE.md`, `EMPLOYER_TOOL_APPROVAL_QUESTION_SET.md`, `PROMPT_AND_OUTPUT_RETENTION_NOTE.md`.
- Backlog: `03_BACKLOG/ARTIFACT_BACKLOG.md` rows A-0005, A-0006, A-0022, A-0048, A-0049, A-0050.
- Decision log: D-0040..D-0044 (Phase 6 set).
