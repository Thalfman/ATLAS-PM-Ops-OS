# SESSION_HANDOFF.md

## Session date

2026-05-23

## Current phase

**Phase 5 - Prompt Library (complete)**

## Session objective

Build the Gemini-first, copy-paste-ready prompt library defined by the Phase 5 prompt: create `05_PROMPTS/PROMPT_LIBRARY.md` as the index, add a reusable 14-section prompt card template, author the 11 paired prompts that the backlog enumerates (one per AI-drafting workflow per D-0034), add the two utility prompts the Phase 5 prompt requires (universal safety precheck and prompt critique / output QA), wire each paired W-NN card's §15 cross-reference to the actual P-NN file, and reconcile the backlog. No new backlog rows added; existing prompt-library rows flipped to Ready for personal use. Phase 6 prompts come in the next session.

## Source-of-truth review

Confirm:

- [x] Read `00_MASTER_CONTEXT/MASTER_CONTEXT.md` at session start.
- [x] Read the previous `09_HANDOFFS/SESSION_HANDOFF.md` at session start.
- [x] Working directory confirmed as `C:\Users\thalf\OneDrive\Documents\ATLAS-PM-Ops-OS`.
- [x] Phase prompt `05_PROMPTS/PHASE_PROMPTS/PHASE_05_PROMPT_LIBRARY.md` consulted.
- [x] Phase 3 governance bundle (`DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`) re-read to confirm citation pattern.
- [x] Phase 4 workflow card template and 11 paired workflow cards re-read to keep each P-NN aligned with the corresponding W-NN's §5/§6/§7/§9/§13/§14.

## Files changed

| Path | Type of change | Summary |
|---|---|---|
| `05_PROMPTS/PROMPT_LIBRARY.md` | added | Library index: universal prompt rules, governance bundle reference, schema reference, 16-row prompt index table (11 paired + 2 utility + 4 reserved-but-empty positions for W-04/13/14/15), maintenance and decision-log pointer, cross-references. |
| `05_PROMPTS/PROMPT_CARD_TEMPLATE.md` | added | Reusable 14-section prompt template covering the Phase 5 prompt's 7 required fields plus governance envelope, paired-workflow citation, placeholders, failure modes, safety precheck citation, critique pass citation, identity, and cross-references. |
| `05_PROMPTS/P-00-safety-precheck.md` | added | Universal pre-flight safety precheck cited by every paired P-NN card §12. Enforces `DATA_SENSITIVITY_DECISION_MODEL.md` classification flow and `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` pre-flight checklist as a self-administered gate. |
| `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` | added | Post-flight critique pass cited by every paired P-NN card §13. Returns structured findings (trace-to-source, fabricated detail, overclaim, missing fields, tone, W-NN red-flag matches); does not rewrite the draft. |
| `05_PROMPTS/P-01-weekly-status-drafting.md` | added | Pairs W-01 / A-0039. Per-domain pattern Status and reporting. Source-trace appendix discipline. |
| `05_PROMPTS/P-02-meeting-notes-to-actions.md` | added | Pairs W-02 / A-0040. Per-domain pattern Meeting notes to action items. Owner/date "missing field" labeling. |
| `05_PROMPTS/P-03-action-aging-summary.md` | added | Pairs W-03 / A-0041. Per-domain pattern Meeting notes to action items. Aging classification with reason; neutral follow-up drafts. |
| `05_PROMPTS/P-05-schedule-variance-narrative.md` | added | Pairs W-05 / A-0047. Per-domain pattern Schedule outputs. Causes framed as observations; number-trace appendix. |
| `05_PROMPTS/P-06-evm-variance-explanation.md` | added | Pairs W-06 / A-0018. Per-domain pattern Finance, EVM, and project accounting. Recompute discipline baked into the prompt. |
| `05_PROMPTS/P-07-risk-register-cleanup.md` | added | Pairs W-07 / A-0042. Per-domain pattern Risk and issue triage. Condition-consequence rewrite; hygiene-notes list. |
| `05_PROMPTS/P-08-issue-and-discrepancy-triage.md` | added | Pairs W-08 / A-0043. Per-domain pattern Risk and issue triage. Severity and owner stay with Tom; AI proposes investigation questions. |
| `05_PROMPTS/P-09-accounting-reconciliation-narrative.md` | added | Pairs W-09 / A-0019. Per-domain pattern Finance, EVM, and project accounting. Four-view discrepancy structure. |
| `05_PROMPTS/P-10-lessons-learned-capture.md` | added | Pairs W-10 / A-0046. Per-domain pattern SOP and lessons-learned. Process / information-flow / tool framing; no individual blame. |
| `05_PROMPTS/P-11-sop-first-draft.md` | added | Pairs W-11 / A-0045. Per-domain pattern SOP and lessons-learned. Testable steps; owner is a role. |
| `05_PROMPTS/P-12-executive-brief-drafting.md` | added | Pairs W-12 / A-0044. Per-domain pattern Status and reporting. Compress without invention; forward-looking statements marked; source-fact appendix. |
| `04_WORKFLOWS/W-01..W-12.md` (11 paired cards) | updated | §15 "Paired Phase 5 prompt" line rewritten to name the actual P-NN file path with both the P-ID and the backlog A-ID. W-04, W-13, W-14, W-15 left unchanged. |
| `03_BACKLOG/ARTIFACT_BACKLOG.md` | updated | 11 prompt-library rows (A-0018, A-0019, A-0039..A-0047) flipped from `Not started` to `Ready for personal use`; Notes column on each row updated to point at the paired P-NN file and the paired W-NN card. "Current build recommendation" tail paragraph rewritten to mark Phase 5 complete and name Phase 6 as next, with A-0038 and A-0029 noted as optional housekeeping follow-ups. |
| `10_DECISION_LOG/DECISION_LOG.md` | updated | Appended D-0035..D-0039 covering P-NN naming, the 14-section prompt card schema, the hybrid layout, the universal P-00 / P-99 utility-prompt pattern, and the branch deviation. |
| `00_MASTER_CONTEXT/MASTER_CONTEXT.md` | updated | Bumped current build stage to "Phase 5 - Prompt Library (complete)" and rewrote "Immediate objective" to describe the Phase 5 deliverable set and name Phase 6 (First-Week Readiness Kit) as next. |

## Completed work

- Authored `05_PROMPTS/PROMPT_LIBRARY.md` as a navigable index: library purpose, universal prompt rules, governance bundle reference, schema reference, 16-row prompt index table, maintenance notes, cross-references.
- Authored `05_PROMPTS/PROMPT_CARD_TEMPLATE.md` as the reusable 14-section template all paired prompt cards conform to.
- Authored 11 paired prompt cards (P-01..P-03, P-05..P-12) end to end. Each card has all 14 sections; each cites the Phase 3 governance bundle by filename and the paired W-NN card by ID; each pulls Safe inputs, Prohibited inputs, Output format, Human review, Failure modes, and Migration notes directly from the paired W-NN card (no policy re-litigation at the prompt layer).
- Authored two utility prompts: `P-00-safety-precheck.md` (cited by every paired P-NN §12) and `P-99-prompt-critique-and-output-qa.md` (cited by every paired P-NN §13).
- Wired the 11 paired W-NN cards' §15 cross-reference from "(TBD in Phase 5)" to the actual P-NN file path with both P-ID and A-ID. The four unpaired W-NN cards (W-04, W-13, W-14, W-15) left unchanged per D-0034.
- Reconciled `03_BACKLOG/ARTIFACT_BACKLOG.md`: 11 status flips, 11 Notes updates, "Current build recommendation" rewritten.
- Logged five Phase 5 decisions in `10_DECISION_LOG/DECISION_LOG.md` (`D-0035` through `D-0039`) in the same session.
- Updated `00_MASTER_CONTEXT/MASTER_CONTEXT.md` to mark Phase 5 complete and name Phase 6 as the next objective.
- Worked Phase 5 on branch `claude/atlas-pm-ops-phase-UXSqk` (deviation from the `feat/phase-NN-<slug>` convention is documented in D-0039, parallel to D-0033 for Phase 4).

## Decisions made

| Decision | Rationale | File or area impacted |
|---|---|---|
| Adopt `P-NN-<slug>.md` naming with reserved-but-empty gaps at P-04, P-13, P-14, P-15 to mirror the W-NN pairing visibly; utility prompts at P-00 and P-99. | Stable IDs across phases; reserved gaps make the 11/15 pairing visible at a glance and prevent re-litigation. | `05_PROMPTS/` and the library index. |
| Adopt a 14-section prompt card schema (7 required Phase 5 fields + governance envelope + paired-workflow citation + placeholders + failure modes + safety precheck + critique pass + identity + cross-references). | One named schema prevents per-prompt reinvention and structurally aligns each P-NN with its paired W-NN. | `05_PROMPTS/PROMPT_CARD_TEMPLATE.md` and all 11 paired prompts. |
| Structure `05_PROMPTS/` as a hybrid (index + template + per-prompt files + 2 utility prompts) rather than a single long file. | 14-section per-prompt files would make a single library file merge-hostile; per-file structure parallels Phase 4 (D-0031) and gives Codex review per-line precision. | `05_PROMPTS/` layout. |
| Author `P-00-safety-precheck.md` and `P-99-prompt-critique-and-output-qa.md` once and cite from every paired P-NN §12 and §13 respectively, rather than restating the precheck and critique in each card. Neither is a new backlog row; both are tracked in the library index. | One canonical precheck and one canonical critique prevent drift across 11 paired prompts. Tracking utility prompts in the library index matches the existing precedent for template files. | `05_PROMPTS/` and every paired prompt's §12/§13. |
| Perform Phase 5 on branch `claude/atlas-pm-ops-phase-UXSqk` rather than the conventional `feat/phase-05-prompt-library`. CLAUDE.md commit and branch policy otherwise applies. | The branch was constrained by the operating environment before the session began (parallel to D-0033 for Phase 4); switching mid-flight would create churn without benefit. Deviation is narrow, not a precedent. | Git. |

These decisions are logged in this session as `D-0035` through `D-0039` in `10_DECISION_LOG/DECISION_LOG.md`, in the same order as the table above.

## Safety review

Confirm:

- [x] No real employer data used.
- [x] No classified data used.
- [x] No CUI used.
- [x] No ITAR or export-controlled data used.
- [x] No proprietary, customer, contract, internal schedule, internal finance, or internal technical data used.
- [x] No real program names, real meeting notes, real Microsoft Project files, or real project accounting exports used.
- [x] All examples are synthetic, public, generic, fictional, or user-created. Every prompt uses placeholders (`[SYNTHETIC_PROJECT_NAME]`, `[APPROVED_INPUT]`, `[FICTIONAL_VARIANCE]`, `[PLACEHOLDER_OWNER]`, `[SYNTHETIC_PERIOD]`, `[FICTIONAL_ACTIVITY_ID]`, `[SYNTHETIC_OWNER_ROLE]`, `[SYNTHETIC_EVENT_TITLE]`, `[SYNTHETIC_DATE]`, `[SYNTHETIC_MEETING_TITLE]`, `[STATUS_COLOR_OR_TREND]`, `[CANDIDATE_INPUT]`, `[PAIRED_W_ID]`, `[NAMED_REVIEWER]`, `[CHOSEN_TOOL_ENVIRONMENT]`, `[PAIRED_PROMPT_ID]`, `[PAIRED_WORKFLOW_ID]`, `[AI_OUTPUT]`, `[SOURCE_INPUT]`).
- [x] Human-in-the-loop posture preserved (every paired prompt names the human reviewer, cites the per-domain review pattern, and forbids AI from deciding, approving, escalating, or sending).
- [x] Gemini-first and platform-agnostic posture preserved (prompts use generic "AI assistant" framing and do not assume Gemini-specific syntax).
- [x] No app, package, API, database, deployment, or code scaffolding added.

## Definition-of-done check

Confirm:

- [x] Every artifact created or updated is Markdown-first and portable.
- [x] Every artifact has a clear purpose and an obvious human review step where relevant.
- [x] No artifact assumes access or data Tom may not have during clearance-limited onboarding.
- [x] This handoff file is up to date and contains the next best prompt.
- [x] Significant decisions from this session are logged in `10_DECISION_LOG/DECISION_LOG.md` in this same session (entries `D-0035` through `D-0039`); none deferred.
- [x] Mode-gated commit step from the session-end protocol is satisfied: local-agent mode committed Phase 5 changes on branch `claude/atlas-pm-ops-phase-UXSqk` in small Conventional Commits and will open a PR against `main` at session end.

## Open items

- A-0038 Process Gap Note Workflow remains `Not started` (carried from Phase 4). Build as `W-16-process-gap-note.md` either during Phase 6 (it pairs naturally with the First-Week Readiness Kit's listening discipline) or as a short follow-up session before Phase 6 begins.
- A-0029 Local skill files refresh remains `Not started`. The Phase 5 patterns are now stable along with Phase 4; the three `skills/*/SKILL.md` files can be reviewed against the combined workflow + prompt card schema. Pair with the Phase 6 build or a chore branch.
- Each paired P-NN card's "Number trace" / "Source trace" appendix is described in the §7 prompt text but not exemplified. Phase 7 (Synthetic Demo Pack) is the natural place to add worked examples that exercise the trace appendix end-to-end.

## Risks and cautions

- The prompt library is conservative on purpose. Several prompts (P-05, P-06, P-07, P-08, P-09) explicitly forbid the AI from assigning severity, owner, probability, impact, or accounting cause; that is the intended posture, not a gap.
- P-00's eight-line checklist is the discipline gate for every paired P-NN. If Phase 6+ surfaces a missing precheck condition (e.g., a new tool environment from onboarding), update P-00 in place and let the citation chain propagate; do not patch individual paired prompts.
- P-99's findings list is not a fix list. The reviewer (Tom or the accountable owner) decides what to fix. If Phase 7 demos start treating P-99 output as an auto-fix, raise as a posture issue.
- The 11/15 pairing per D-0034 is fixed. Future phases that surface a new AI-drafting workflow should follow the Phase 4 → Phase 5 sequence: add a W-NN card first, then a paired P-NN with the next available number.

## AI tooling notes

The 11 paired prompts are authored Gemini-first and platform-agnostic. Personal AI tools (Claude, ChatGPT, Gemini consumer) are the default tool environment for personal-preparation use; an Employer-approved AI tool only enters the picture once explicit approval exists for the specific data category, per the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`. Every paired prompt's §7 forbids the AI from deciding, approving, escalating, or sending; AI's role is strictly to structure, compare, summarize, draft, or flag inconsistencies. P-00 sits in front of every prompt as a self-administered gate. P-99 sits after every Strict-intensity prompt as a structured critique pass.

## Recommended next phase or artifact

**Phase 6: First-Week Readiness Kit**

Assemble the conservative kit Tom uses during clearance-limited onboarding. The kit builds on (or hardens) existing seeded artifacts (A-0005 First-Week Discovery Script, A-0006 Executive Narrative Template) and adds the not-started rows (A-0022 Clearance-Limited Value Plan, A-0048 Listening Plan, A-0049 Onboarding Question Set, A-0050 "What I Can Offer This Week" One-Pager). Phase 6 inherits the same Phase 3 governance envelope (data category, tool environment, review intensity, per-domain review pattern) and aligns with W-15 (`W-15-clearance-limited-onboarding.md`) as its operating workflow. The kit must explicitly avoid promising deliverables that depend on restricted access; W-15's "feel-good but undercommit" risk note in §13 carries forward into Phase 6.

Optional housekeeping during or after Phase 6:

- Build A-0038 Process Gap Note as `04_WORKFLOWS/W-16-process-gap-note.md`. The note pattern pairs naturally with the Phase 6 listening plan.
- Refresh A-0029 local skill files (`skills/*/SKILL.md`) against the now-stable Phase 4 workflow card and Phase 5 prompt card schemas.

## Next best prompt

```text
Continue ATLAS PM/Ops OS.

Local repo path:
C:\Users\thalf\OneDrive\Documents\ATLAS-PM-Ops-OS

Source-of-truth files to read first:
1. 00_MASTER_CONTEXT/MASTER_CONTEXT.md
2. 09_HANDOFFS/SESSION_HANDOFF.md
3. 02_ROADMAP/ROADMAP.md
4. 03_BACKLOG/ARTIFACT_BACKLOG.md
5. 04_WORKFLOWS/WORKFLOW_LIBRARY.md
6. 04_WORKFLOWS/W-15-clearance-limited-onboarding.md
7. 05_PROMPTS/PROMPT_LIBRARY.md
8. 06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md
9. 06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md
10. 06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md
11. 06_GOVERNANCE/AI_GOVERNANCE_NOTES.md
12. 07_TEMPLATES/FIRST_WEEK_DISCOVERY_SCRIPT.md
13. 07_TEMPLATES/EXECUTIVE_NARRATIVE.md
14. 05_PROMPTS/PHASE_PROMPTS/PHASE_06_FIRST_WEEK_READINESS_KIT.md

Phase to run:
Phase 6: First-Week Readiness Kit

Phase prompt file:
05_PROMPTS/PHASE_PROMPTS/PHASE_06_FIRST_WEEK_READINESS_KIT.md

Safety boundary (one line):
Use only synthetic, public, generic, fictional, or user-created non-proprietary material. Do not use classified, CUI, ITAR/export-controlled, proprietary, customer, contract, internal schedule, internal finance, internal technical, real meeting note, real Microsoft Project, or real accounting data.

Posture:
Markdown-first, Gemini-first, platform-agnostic, human-in-the-loop, approved-tool-first. Do not add apps, package dependencies, APIs, databases, deployment files, or code scaffolding. Build the First-Week Readiness Kit under 07_TEMPLATES/ (or the location each backlog row names) so that Tom can use it during clearance-limited onboarding without touching restricted content. Cover the existing seeded artifacts (A-0005 First-Week Discovery Script — harden it; A-0006 Executive Narrative Template — harden it) plus the not-started rows (A-0022 Clearance-Limited Value Plan, A-0048 Listening Plan, A-0049 Onboarding Question Set, A-0050 "What I Can Offer This Week" One-Pager). Each artifact cites the Phase 3 governance envelope by name (data category from DATA_SENSITIVITY_DECISION_MODEL.md, tool environment, review intensity from HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md, per-domain review pattern) and references W-15 (W-15-clearance-limited-onboarding.md) as the operating workflow. Each artifact must avoid promising deliverables that depend on restricted access. Log Phase 6 decisions in 10_DECISION_LOG/DECISION_LOG.md in the same session. Update 09_HANDOFFS/SESSION_HANDOFF.md at the end with the Phase 7 next best prompt. Optional housekeeping: build A-0038 Process Gap Note Workflow as 04_WORKFLOWS/W-16-process-gap-note.md (paired Phase 5 prompt: none expected; it is a personal-note workflow), and refresh A-0029 local skill files against the Phase 4 / 5 schemas.
```
