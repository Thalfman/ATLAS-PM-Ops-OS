# SESSION_HANDOFF.md

## Session date

2026-05-23

## Current phase

**Phase 7 - Synthetic Demo Pack (complete)**

## Session objective

Build the Synthetic Demo Pack defined by the Phase 7 prompt: harden the seeded A-0007 Synthetic Status Pack Demo with paired W-NN / P-NN structure and add the four not-started rows (A-0023 Synthetic Schedule Variance Demo, A-0024 Synthetic Action Tracker Demo, A-0051 Synthetic Discrepancy Triage Demo, A-0052 Synthetic Risk Register Cleanup Demo). Add a pack index (`SYNTHETIC_DEMO_PACK.md`) and a shared synthetic project scenario (`SYNTHETIC_PROJECT_SCENARIO.md`) — both utility files tracked in the pack index, not the backlog. Each demo opens with a bold synthetic label, walks input → AI step → human review → output as a pattern, cites the Phase 3 governance envelope by filename, and pairs against a specific Phase 4 W-NN and Phase 5 P-NN. No new backlog rows; five existing rows flipped to `Ready for personal use`. Phase 8 (Microsoft Project and Schedule Integrity Track) is next.

## Source-of-truth review

Confirm:

- [x] Read `00_MASTER_CONTEXT/MASTER_CONTEXT.md` at session start.
- [x] Read the previous `09_HANDOFFS/SESSION_HANDOFF.md` at session start.
- [x] Working directory confirmed as `C:\Users\thalf\OneDrive\Documents\ATLAS-PM-Ops-OS`.
- [x] Phase prompt `05_PROMPTS/PHASE_PROMPTS/PHASE_07_SYNTHETIC_DEMO_PACK.md` consulted.
- [x] Seeded `08_SYNTHETIC_DEMOS/SYNTHETIC_STATUS_PACK_DEMO.md` re-read before hardening.
- [x] Phase 4 W-01, W-02, W-03, W-05, W-07, W-08, W-12 cards re-read to confirm paired-card structure and §7 output formats.
- [x] Phase 5 P-01, P-02, P-03, P-05, P-07, P-08, P-12 prompt cards confirmed by filename for citation in each demo's AI step.
- [x] Phase 3 governance bundle confirmed (`DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`).

## Files changed

| Path | Type of change | Summary |
|---|---|---|
| `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md` | added | Pack index: pack rules, pack index table, in-conversation usage guidance, maintenance notes, cross-references. Mirrors the Phase 4 / 5 / 6 hybrid pattern. |
| `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md` | added | Shared synthetic backdrop: Project Northstar Demo identity, fictional cast (PM/Ops, Team Lead, Workstream A / B / C Leads, Reporting Coordinator, Placeholder Owners), milestones M-01..M-06, workstreams A / B / C, governance envelope, binding synthetic data rules. Utility file tracked in the pack index per D-0048. |
| `08_SYNTHETIC_DEMOS/SYNTHETIC_STATUS_PACK_DEMO.md` | updated | A-0007 hardened: added paired W-01 / W-12, paired P-01 / P-12, governance envelope citation, shared-scenario reference, full input → AI step → human review → output walkthrough, sign-off block, cross-demo references. |
| `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md` | added | A-0023: pairs W-05 / P-05, fictional schedule snapshot showing +2 to +4 day variances on Project Northstar Demo, AI draft, human-review against the "Schedule outputs" pattern, final narrative. |
| `08_SYNTHETIC_DEMOS/SYNTHETIC_ACTION_TRACKER_DEMO.md` | added | A-0024: two halves on the same scenario — extraction (W-02 / P-02) from fictional meeting notes and aging (W-03 / P-03) from a fictional tracker snapshot. AI flags missing fields and ambiguous ownership; Tom resolves. |
| `08_SYNTHETIC_DEMOS/SYNTHETIC_DISCREPANCY_TRIAGE_DEMO.md` | added | A-0051: pairs W-08 / P-08, six fictional issue notes, AI triage table without severity / owner assignments, Tom assigns. Cross-references the schedule variance demo and the action tracker demo. |
| `08_SYNTHETIC_DEMOS/SYNTHETIC_RISK_REGISTER_CLEANUP_DEMO.md` | added | A-0052: pairs W-07 / P-07, seven-row fictional pre-cleanup register, AI flags retirement candidates and merge candidates without rewriting non-conditioned entries, owners decide. |
| `03_BACKLOG/ARTIFACT_BACKLOG.md` | updated | Five synthetic-demos rows (A-0007, A-0023, A-0024, A-0051, A-0052) flipped from `Seeded` / `Not started` to `Ready for personal use` with Notes columns pointing at the demo file paths, the paired W-NN / P-NN, the per-domain review pattern, and the pack index. "Current build recommendation" tail rewritten to mark Phase 7 complete and name Phase 8 as next. |
| `10_DECISION_LOG/DECISION_LOG.md` | updated | Appended D-0045..D-0048 covering the Phase 7 branch (canonical convention), the pack hybrid layout, the per-demo structure rules, and the shared-scenario utility-file status. |
| `00_MASTER_CONTEXT/MASTER_CONTEXT.md` | updated | Bumped current build stage to "Phase 7 - Synthetic Demo Pack (complete)" and rewrote "Immediate objective" to describe the seven-file pack and name Phase 8 (Microsoft Project and Schedule Integrity Track) as next. |

## Completed work

- Authored `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md` as the pack index with pack rules, pack index table, in-conversation usage guidance, and maintenance notes.
- Authored `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md` as the shared backdrop (utility per D-0048). Names the fictional cast, milestones, and workstreams that every demo draws from.
- Authored four new demos (A-0023, A-0024, A-0051, A-0052), each with the four-step walkthrough, the governance envelope, the paired W-NN / P-NN, the per-domain review pattern, and cross-references to the other demos that share the scenario.
- Hardened the seeded A-0007 demo: kept the original synthetic inputs intact and added the paired W-NN / P-NN structure, the governance envelope, the explicit walkthrough sections, and a sign-off block.
- Reconciled `03_BACKLOG/ARTIFACT_BACKLOG.md`: five status flips, five Notes updates, "Current build recommendation" rewritten.
- Logged four Phase 7 decisions in `10_DECISION_LOG/DECISION_LOG.md` (D-0045 through D-0048) in the same session.
- Updated `00_MASTER_CONTEXT/MASTER_CONTEXT.md` to mark Phase 7 complete and name Phase 8 as the next objective.
- Worked Phase 7 on branch `feat/phase-07-synthetic-demo-pack` per the canonical convention (D-0045), returning to the convention after the env-constrained Phase 4 / 5 / 6 branches.

## Decisions made

| Decision | Rationale | File or area impacted |
|---|---|---|
| Perform Phase 7 on branch `feat/phase-07-synthetic-demo-pack` per the canonical `CLAUDE.md` convention. | The environment did not pre-allocate a constrained branch for Phase 7; returning to the convention keeps the deviation pattern (D-0033, D-0039, D-0040) narrow rather than precedential. | Git. |
| Structure Phase 7 as a hybrid: pack index + shared scenario + five per-demo files under `08_SYNTHETIC_DEMOS/`. | Per-demo files parallel the Phase 4 / 5 / 6 hybrids (D-0031, D-0037, D-0041); each demo names a specific paired W-NN / P-NN and a per-domain review pattern. | `08_SYNTHETIC_DEMOS/` layout. |
| Every demo names paired W-NN / P-NN by ID, opens with a bold synthetic label, walks input → AI step → human review → output as a pattern, cites the Phase 3 envelope by filename. | Makes the migration path explicit, makes the demo a pattern rather than a product, and avoids restating policy at the demo layer. Mirrors D-0029 / D-0036 / D-0042. | All Phase 7 demo files. |
| Shared synthetic project scenario authored once as `SYNTHETIC_PROJECT_SCENARIO.md`, tracked in the pack index, not the backlog. Parallel to P-00 / P-99 (D-0038) and the AI Integration Discussion Guide (D-0043). | One coherent backdrop makes demos walk-through-able; tracking utility files in pack indexes matches existing precedent. | `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md` and the pack index. |

These decisions are logged in this session as `D-0045` through `D-0048` in `10_DECISION_LOG/DECISION_LOG.md`, in the same order as the table above.

## Safety review

Confirm:

- [x] No real employer data used.
- [x] No classified data used.
- [x] No CUI used.
- [x] No ITAR or export-controlled data used.
- [x] No proprietary, customer, contract, internal schedule, internal finance, or internal technical data used.
- [x] No real program names, real meeting notes, real Microsoft Project files, or real project accounting exports used.
- [x] All examples are obviously synthetic: Project Northstar Demo with fictional cast (PM/Ops, Team Lead, Workstream A / B / C Leads, Reporting Coordinator, Placeholder Owner 1 / 2 / 3), fictional milestones M-01..M-06, fictional activity IDs NS-A-01..03, NS-B-01..02, NS-C-01..02, fictional risk IDs R-001 / R-002, fictional issue IDs I-001 / I-002, fictional action IDs A-001..A-106. Every demo opens with a bold synthetic label.
- [x] Human-in-the-loop posture preserved: every demo names the named human reviewer (Tom), cites the per-domain review pattern from `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, and shows AI flagging rather than inventing.
- [x] Gemini-first and platform-agnostic posture preserved: demos use generic "AI assistant" / "Personal AI tool" framing and Gemini-first invocation language with no product-specific syntax.
- [x] No app, package, API, database, deployment, or code scaffolding added.

## Definition-of-done check

Confirm:

- [x] Every artifact created or updated is Markdown-first and portable.
- [x] Every artifact has a clear purpose and an obvious human review step where relevant. Each demo's "Step 4 - Human review" section names the per-domain pattern and lists the reviewer's checks.
- [x] No artifact assumes access or data Tom may not have. Every input is obviously synthetic.
- [x] This handoff file is up to date and contains the next best prompt.
- [x] Significant decisions from this session are logged in `10_DECISION_LOG/DECISION_LOG.md` in this same session (entries `D-0045` through `D-0048`); none deferred.
- [x] Mode-gated commit step from the session-end protocol is satisfied: local-agent mode commits Phase 7 changes on branch `feat/phase-07-synthetic-demo-pack` in small Conventional Commits and opens a PR against `main` at session end.

## Open items

- A-0038 Process Gap Note Workflow remains `Not started` (carried from Phase 4 / 6). It pairs naturally with the Phase 6 listening plan; build as `W-16-process-gap-note.md` either during Phase 8 or as a short follow-up session.
- A-0029 Local skill files refresh remains `Not started`. Pair with the Phase 8 build or a chore branch.
- Optional Phase 7 demos that the prompt mentions but were deliberately not built: EVM variance explanation, accounting reconciliation narrative, lessons learned. Rationale lives in `SYNTHETIC_DEMO_PACK.md` "Pack index" section: those demos require synthetic finance workbooks (Phase 9 — A-0054, A-0055, A-0056) or lessons-learned templates (Phase 10 — A-0058) that are not built yet. Sequenced rather than skipped.
- Phase 8 will need a synthetic schedule workbook (A-0053) that the Phase 7 schedule variance demo can be re-exercised against; the demo's compact schedule snapshot is sufficient for Phase 7 but a richer workbook helps Phase 8 schedule-health work.

## Risks and cautions

- The demo pack is conservative on purpose. Every demo is labeled fictional, shows AI flagging rather than deciding, and refuses to commit deployment-readiness. Review feedback that tries to add real-data fidelity, real program/customer references, or "polish for executive use" should be redirected to the Phase 11 migration plan, not the demo pack.
- Cross-demo references (A-105 → R-001; row 6 → schedule variance demo; etc.) keep the pack coherent but also create review burden if a future change touches one demo's cast or milestones. Use the shared scenario file as the single source of truth and back-port relevant per-demo updates in the same session if the scenario changes.
- The Phase 7 prompt's optional EVM / accounting / lessons demos are sequenced to Phase 9 / 10 rather than built here. If a Codex reviewer expects them in Phase 7, the rationale in `SYNTHETIC_DEMO_PACK.md` "Pack index" section explains the decision.

## AI tooling notes

The Phase 7 demos are authored Gemini-first and platform-agnostic. Personal AI tools (Claude, ChatGPT, Gemini consumer) are the default tool environment for the AI-step exercises because the inputs are Synthetic per the data-routing rules in `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. Migration to Employer-approved AI tools for real data requires re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`; the per-demo §14 references in the paired W-NN cards already carry that guidance forward. The pack rules forbid blending real data into demos to "make them more realistic" — that move would defeat the purpose of the pack and is one of the standing risks called out above.

## Recommended next phase or artifact

**Phase 8: Microsoft Project and Schedule Integrity Track**

Build schedule-health, variance-narrative, and reporting-quality artifacts using synthetic schedules. Backlog rows: A-0015 (Microsoft Project Schedule Health Checklist), A-0016 (Schedule Variance Narrative Template), A-0053 (Synthetic Schedule Workbook). Phase 8 hardens against the Phase 4 W-04 (schedule health) and W-05 (schedule variance) workflow cards, exercises the Phase 5 P-05 prompt, and pairs against the Phase 7 schedule variance demo (which uses a compact synthetic schedule snapshot). A richer synthetic schedule workbook lets the schedule-health checklist run against multi-week data with critical path identification, slack, and dependencies.

Optional housekeeping during or after Phase 8:

- Build A-0038 Process Gap Note as `04_WORKFLOWS/W-16-process-gap-note.md`. Pairs naturally with the Phase 6 listening plan.
- Refresh A-0029 local skill files (`skills/*/SKILL.md`) against the Phase 4 / 5 / 6 / 7 schemas.

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
5. 04_WORKFLOWS/W-04-schedule-health-review.md
6. 04_WORKFLOWS/W-05-schedule-variance-narrative.md
7. 05_PROMPTS/P-05-schedule-variance-narrative.md
8. 08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md
9. 08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md
10. 06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md
11. 06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md
12. 05_PROMPTS/PHASE_PROMPTS/PHASE_08_MICROSOFT_PROJECT_AND_SCHEDULE_INTEGRITY_TRACK.md

Phase to run:
Phase 8: Microsoft Project and Schedule Integrity Track

Phase prompt file:
05_PROMPTS/PHASE_PROMPTS/PHASE_08_MICROSOFT_PROJECT_AND_SCHEDULE_INTEGRITY_TRACK.md

Safety boundary (one line):
Use only synthetic, public, generic, fictional, or user-created non-proprietary material. Do not use classified, CUI, ITAR/export-controlled, proprietary, customer, contract, internal schedule, internal finance, internal technical, real meeting note, real Microsoft Project, or real accounting data.

Posture:
Markdown-first, Gemini-first, platform-agnostic, human-in-the-loop, approved-tool-first. Do not add apps, package dependencies, APIs, databases, deployment files, or code scaffolding. Build under a phase folder (likely `11_MICROSOFT_PROJECT/` per the existing repo structure if it exists, otherwise add the three artifacts inside `08_SYNTHETIC_DEMOS/` or a new dedicated folder consistent with `02_ROADMAP/ROADMAP.md` Phase 8 layout). Cover A-0015 (Microsoft Project Schedule Health Checklist — generic checklist, never real `.mpp`), A-0016 (Schedule Variance Narrative Template — pair with W-05 / P-05 and the Phase 7 schedule variance demo), and A-0053 (Synthetic Schedule Workbook — Markdown/CSV-style fictional schedule with critical path, slack, dependencies; references Project Northstar Demo from `SYNTHETIC_PROJECT_SCENARIO.md`). Cite the Phase 3 governance envelope by filename on each artifact. Log Phase 8 decisions in 10_DECISION_LOG/DECISION_LOG.md in the same session. Update 09_HANDOFFS/SESSION_HANDOFF.md at the end with the Phase 9 next best prompt. Optional housekeeping: build A-0038 Process Gap Note Workflow as 04_WORKFLOWS/W-16-process-gap-note.md, and refresh A-0029 local skill files.
```
