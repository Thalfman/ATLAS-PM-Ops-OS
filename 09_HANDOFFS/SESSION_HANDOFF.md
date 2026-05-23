# SESSION_HANDOFF.md

## Session date

2026-05-23

## Current phase

**Phase 4 - Workflow Library (complete)**

## Session objective

Build the manual-first PM/Ops workflow library defined by the Phase 4 prompt: rewrite `04_WORKFLOWS/WORKFLOW_LIBRARY.md` as a structured library; add a reusable card template; author the 15 workflows the Phase 4 prompt enumerates as per-workflow files; have each card cite the Phase 3 governance bundle by name (data category, tool environment, review intensity, per-domain review pattern). No prompts authored in this phase; prompts come in Phase 5.

## Source-of-truth review

Confirm:

- [x] Read `00_MASTER_CONTEXT/MASTER_CONTEXT.md` at session start.
- [x] Read the previous `09_HANDOFFS/SESSION_HANDOFF.md` at session start.
- [x] Working directory confirmed as `C:\Users\thalf\OneDrive\Documents\ATLAS-PM-Ops-OS`.
- [x] Phase prompt `05_PROMPTS/PHASE_PROMPTS/PHASE_04_WORKFLOW_LIBRARY.md` consulted.
- [x] Phase 3 governance bundle re-read (data sensitivity model, human review and auditability model, AI tool approval strategy, AI governance notes) to confirm citation pattern.

## Files changed

| Path | Type of change | Summary |
|---|---|---|
| `04_WORKFLOWS/WORKFLOW_LIBRARY.md` | updated | Rewritten as the library index: universal rules, governance bundle reference, schema reference, 15-row workflow index table, maintenance notes. The 8 previous starter cards have been folded into the matching W-NN files. |
| `04_WORKFLOWS/WORKFLOW_CARD_TEMPLATE.md` | added | Reusable 16-section workflow template (12 Phase 4 required fields + 4 governance citations + identity + cross-references). |
| `04_WORKFLOWS/W-01-weekly-status-report.md` | added | Workflow card. Pairs with A-0008. Data category Synthetic / Tom-personal; review intensity Standard; per-domain pattern Status and reporting. |
| `04_WORKFLOWS/W-02-meeting-notes-to-actions.md` | added | Workflow card. Pairs with A-0009. Data category Tom-personal; review intensity Standard; per-domain pattern Meeting notes to action items. |
| `04_WORKFLOWS/W-03-action-item-aging.md` | added | Workflow card. Pairs with A-0010. Data category Tom-personal; review intensity Standard; per-domain pattern Meeting notes to action items. |
| `04_WORKFLOWS/W-04-schedule-health-review.md` | added | Workflow card. Pairs with Phase 8 deliverable A-0015. Data category Synthetic; review intensity Standard; per-domain pattern Schedule outputs. |
| `04_WORKFLOWS/W-05-schedule-variance-narrative.md` | added | Workflow card. Pairs with Phase 8 deliverable A-0016. Data category Synthetic; review intensity Standard; per-domain pattern Schedule outputs. |
| `04_WORKFLOWS/W-06-evm-variance-explanation.md` | added | Workflow card. Pairs with new backlog row A-0066. Data category Synthetic; review intensity Standard; per-domain pattern Finance, EVM, and project accounting. |
| `04_WORKFLOWS/W-07-risk-register-cleanup.md` | added | Workflow card. Pairs with A-0011. Data category Synthetic; review intensity Standard; per-domain pattern Risk and issue triage. |
| `04_WORKFLOWS/W-08-issue-and-discrepancy-triage.md` | added | Workflow card. Pairs with A-0012. Data category Synthetic; review intensity Standard; per-domain pattern Risk and issue triage. |
| `04_WORKFLOWS/W-09-accounting-reconciliation-narrative.md` | added | Workflow card. Pairs with A-0036. Data category Synthetic; review intensity Standard; per-domain pattern Finance, EVM, and project accounting. |
| `04_WORKFLOWS/W-10-lessons-learned-capture.md` | added | Workflow card. Pairs with Phase 10 deliverable A-0013. Data category Synthetic; review intensity Standard; per-domain pattern SOP and lessons-learned. |
| `04_WORKFLOWS/W-11-sop-draft-generation.md` | added | Workflow card. Pairs with Phase 10 deliverable A-0014. Data category Synthetic; review intensity Standard; per-domain pattern SOP and lessons-learned. |
| `04_WORKFLOWS/W-12-executive-brief-generation.md` | added | Workflow card. Pairs with new backlog row A-0067. Data category Synthetic / Tom-personal; review intensity Standard; per-domain pattern Status and reporting. |
| `04_WORKFLOWS/W-13-cross-tool-mismatch-investigation.md` | added | Workflow card. Pairs with A-0037. Data category Synthetic; review intensity Standard; per-domain patterns Schedule and Finance, EVM, and project accounting. |
| `04_WORKFLOWS/W-14-google-workspace-knowledge.md` | added | Workflow card. Pairs with A-0020. Data category Public / Synthetic; tool environment Employer-approved AI tool (Workspace); review intensity Standard; per-domain pattern SOP and lessons-learned. |
| `04_WORKFLOWS/W-15-clearance-limited-onboarding.md` | added | Workflow card. Pairs with new backlog row A-0068. Data category Tom-personal; tool environment ATLAS-local Markdown / Personal AI tool; review intensity Light; per-domain pattern Status and reporting. |
| `03_BACKLOG/ARTIFACT_BACKLOG.md` | updated | Appended A-0066, A-0067, A-0068 under Workflow library. Updated Notes column for A-0008, A-0009, A-0010, A-0011, A-0012, A-0013, A-0014, A-0015, A-0016, A-0020, A-0036, A-0037 to point at the matching W-NN file. Flipped Status to `Ready for personal use` for A-0008, A-0009, A-0010, A-0011, A-0012, A-0020, A-0036, A-0037 plus the three new rows. Rewrote tail "Current build recommendation" paragraph to mark Phase 4 complete and name Phase 5 as next. A-0038 (Process Gap Note) remains `Not started` for a follow-up session. |
| `10_DECISION_LOG/DECISION_LOG.md` | updated | Appended D-0029..D-0033 covering the 16-section card schema, W-NN naming, hybrid file structure, backlog reconciliation, and the branch deviation. |
| `00_MASTER_CONTEXT/MASTER_CONTEXT.md` | updated | Bumped current build stage to Phase 4 complete; rewrote the Immediate objective paragraph to describe the Phase 4 deliverable set and name Phase 5 as next. |

## Completed work

- Rewrote `04_WORKFLOWS/WORKFLOW_LIBRARY.md` as a navigable index: library purpose, universal workflow rules, governance bundle reference, schema reference, 15-row workflow index table, maintenance notes, cross-references.
- Authored `04_WORKFLOWS/WORKFLOW_CARD_TEMPLATE.md` as the reusable 16-section template all cards conform to.
- Authored 15 per-workflow card files (`W-01` through `W-15`) covering the Phase 4 prompt's enumerated workflow list end to end. Each card has all 12 required fields and cites all four Phase 3 governance files by filename.
- Folded the 8 previous starter cards into the matching W-NN files; no card content is duplicated between the library index and the per-workflow files.
- Reconciled `03_BACKLOG/ARTIFACT_BACKLOG.md`: three new rows, twelve Notes updates, eleven Status flips, "Current build recommendation" rewritten.
- Logged five Phase 4 decisions in `10_DECISION_LOG/DECISION_LOG.md` (`D-0029` through `D-0033`) in the same session.
- Updated `00_MASTER_CONTEXT/MASTER_CONTEXT.md` to mark Phase 4 complete and name Phase 5 as the next objective.
- Worked Phase 4 on branch `claude/phase-4-planning-4142G` (deviation from the `feat/phase-NN-<slug>` convention is documented in D-0033).

## Decisions made

| Decision | Rationale | File or area impacted |
|---|---|---|
| Adopt a 16-section workflow card schema (12 Phase 4 fields + 4 governance citations + identity + cross-references). | A single named schema prevents per-card reinvention and gives Phase 5 prompts a stable per-card anchor. | `04_WORKFLOWS/WORKFLOW_CARD_TEMPLATE.md` and all 15 W-NN files. |
| Adopt `W-NN-<slug>.md` naming, append-only, numbering follows the Phase 4 prompt's enumerated list 1-15. | Stable IDs let prompts, demos, and migration plans reference workflows unambiguously across phases. Mirrors append-only A-ID rule (D-0017). | `04_WORKFLOWS/` and the library index. |
| Structure `04_WORKFLOWS/` as a hybrid (index + reusable template + one file per workflow). | The 16-section schema makes single-file storage merge-hostile; per-workflow files give Codex review per-line precision. | `04_WORKFLOWS/` layout; rewrites `WORKFLOW_LIBRARY.md` as an index. |
| Add three new Phase 4 backlog rows (A-0066, A-0067, A-0068); reuse later-phase A-IDs (A-0013, A-0014, A-0015, A-0016) for the four workflows whose primary backlog assets live in Phases 8 and 10. A-0038 remains `Not started` for a follow-up session. | Promotes truly missing workflows to Phase 4 backlog rows; avoids two-rows-one-workflow drift for later-phase deliverables. | `03_BACKLOG/ARTIFACT_BACKLOG.md`. |
| Perform Phase 4 on branch `claude/phase-4-planning-4142G` rather than the conventional `feat/phase-04-workflow-library`. CLAUDE.md commit and branch policy otherwise applies. | The branch was constrained by the operating environment before the session began; switching mid-flight would create churn without benefit. Deviation is narrow, not a precedent. | Git. |

These decisions are logged in this session as `D-0029` through `D-0033` in `10_DECISION_LOG/DECISION_LOG.md`, in the same order as the table above.

## Safety review

Confirm:

- [x] No real employer data used.
- [x] No classified data used.
- [x] No CUI used.
- [x] No ITAR or export-controlled data used.
- [x] No proprietary, customer, contract, internal schedule, internal finance, or internal technical data used.
- [x] No real program names, real meeting notes, real Microsoft Project files, or real project accounting exports used.
- [x] All examples are synthetic, public, generic, fictional, or user-created.
- [x] Human-in-the-loop posture preserved (every workflow card cites the human review point pattern and names the reviewer).
- [x] Gemini-first and platform-agnostic posture preserved.
- [x] No app, package, API, database, deployment, or code scaffolding added.

## Definition-of-done check

Confirm:

- [x] Every artifact created or updated is Markdown-first and portable.
- [x] Every artifact has a clear purpose and an obvious human review step where relevant.
- [x] No artifact assumes access or data Tom may not have during clearance-limited onboarding.
- [x] This handoff file is up to date and contains the next best prompt.
- [x] Significant decisions from this session are logged in `10_DECISION_LOG/DECISION_LOG.md` in this same session (entries `D-0029` through `D-0033`); none deferred.
- [x] Mode-gated commit step from the session-end protocol is satisfied: local-agent mode committed Phase 4 changes on branch `claude/phase-4-planning-4142G` in small Conventional Commits and will open a PR against `main` at session end.

## Open items

- A-0038 Process Gap Note Workflow is `Not started` and not in the Phase 4 prompt's minimum 15. It is the obvious Phase 4 follow-up; build it as `W-16-process-gap-note.md` in a short follow-up session once Phase 5 begins, or alongside Phase 6 (First-Week Readiness Kit) which depends on it.
- A-0029 Local skill files refresh is `Not started`. The Phase 4 patterns are now stable, so the three `skills/*/SKILL.md` files can be reviewed against the workflow card schema. Pair this with the Phase 5 build or a chore branch.
- Phase 5 prompts must name the W-ID they pair against. The Phase 5 phase prompt (`05_PROMPTS/PHASE_PROMPTS/PHASE_05_PROMPT_LIBRARY.md`) may benefit from a short pre-Phase-5 reading pass to confirm pairing.
- Each W-NN card's §15 "Cross-references" names a paired Phase 5 prompt with its A-ID; confirm those A-IDs still align with the actual backlog when Phase 5 begins.

## Risks and cautions

- The workflow library is conservative on purpose. Several cards (W-04, W-05, W-06, W-09, W-13) explicitly stop short of recommending estimates, dates, or accounting determinations; that is the intended posture, not a gap.
- W-15 (clearance-limited onboarding) carries the highest "feel-good but undercommit" risk; the card explicitly forbids commitments outside cleared scope. Resist temptation to widen during real onboarding without manager agreement.
- Phase 5 prompts will pair against each W-NN card. If Phase 5 introduces a richer prompt schema, back-port the workflow card §15 cross-references rather than redefining the pairing.
- A-0038 Process Gap Note's deferral is a personal-preparation choice, not a safety choice. Pick it up before Phase 6 if onboarding starts.

## AI tooling notes

The 15 workflow cards are authored Gemini-first and platform-agnostic. Personal AI tools (Claude, ChatGPT, Gemini consumer) are the default tool environment for personal-preparation use; an Employer-approved AI tool only enters the picture once explicit approval exists for the specific data category, per the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`. The cards explicitly forbid AI from making commitments, sending messages, escalating, or rendering accounting determinations.

## Recommended next phase or artifact

**Phase 5: Prompt Library**

Author Gemini-first prompts that pair against the 11 of 15 W-NN workflow cards that are primarily AI-drafting workflows. The backlog defines exactly 11 Phase 5 prompt rows (A-0018, A-0019, A-0039 through A-0047); they map to W-01, W-02, W-03, W-05, W-06, W-07, W-08, W-09, W-10, W-11, W-12. The remaining four workflows (W-04 schedule health, W-13 cross-tool mismatch, W-14 Google Workspace knowledge, W-15 clearance-limited onboarding) are structural, investigative, information-management, or personal-planning workflows; their §15 cross-references explicitly state "Paired Phase 5 prompt: none" and explain why. Phase 5 should not invent additional prompts to force a 15/15 pairing.

Each prompt cites the same Phase 3 governance bundle by name (data category from `DATA_SENSITIVITY_DECISION_MODEL.md`, tool environment, review intensity from `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, per-domain review pattern) and names the paired W-NN card by ID. As an optional housekeeping pass, build A-0038 Process Gap Note as `W-16-process-gap-note.md` (paired Phase 5 prompt: none expected; it is a personal-note workflow).

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
6. 04_WORKFLOWS/WORKFLOW_CARD_TEMPLATE.md
7. 06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md
8. 06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md
9. 06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md
10. 06_GOVERNANCE/AI_GOVERNANCE_NOTES.md
11. 05_PROMPTS/PHASE_PROMPTS/PHASE_05_PROMPT_LIBRARY.md

Phase to run:
Phase 5: Prompt Library

Phase prompt file:
05_PROMPTS/PHASE_PROMPTS/PHASE_05_PROMPT_LIBRARY.md

Safety boundary (one line):
Use only synthetic, public, generic, fictional, or user-created non-proprietary material. Do not use classified, CUI, ITAR/export-controlled, proprietary, customer, contract, internal schedule, internal finance, internal technical, real meeting note, real Microsoft Project, or real accounting data.

Posture:
Markdown-first, Gemini-first, platform-agnostic, human-in-the-loop, approved-tool-first. Do not add apps, package dependencies, APIs, databases, deployment files, or code scaffolding. Author Gemini-first prompts under 05_PROMPTS/ that pair against the 11 of 15 W-NN workflow cards that are primarily AI-drafting workflows. The 11 paired W-NN cards are W-01, W-02, W-03, W-05, W-06, W-07, W-08, W-09, W-10, W-11, W-12. The remaining four cards (W-04, W-13, W-14, W-15) have "Paired Phase 5 prompt: none" in their section 15 by design; do not invent prompts for them. Each prompt cites the Phase 3 governance bundle by name (data category per DATA_SENSITIVITY_DECISION_MODEL.md, tool environment, review intensity per HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md, per-domain review pattern) and names the paired W-NN card by ID. Backlog rows A-0018, A-0019, A-0039..A-0047 enumerate exactly 11 Phase 5 prompts; each paired W-NN card's section 15 names the paired prompt's A-ID. Log Phase 5 decisions in 10_DECISION_LOG/DECISION_LOG.md in the same session. Update 09_HANDOFFS/SESSION_HANDOFF.md at the end with the Phase 6 next best prompt. Optional housekeeping: build A-0038 Process Gap Note Workflow as 04_WORKFLOWS/W-16-process-gap-note.md before or after the Phase 5 prompts.
```
