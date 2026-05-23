# SESSION_HANDOFF.md

## Session date

2026-05-23

## Current phase

**Phase 6 - First-Week Readiness Kit (complete)**

## Session objective

Build the conservative First-Week Readiness Kit defined by the Phase 6 prompt: harden the two seeded templates (A-0005 First-Week Discovery Script, A-0006 Executive Narrative Template) and add the four not-started rows (A-0022 Clearance-Limited Value Plan, A-0048 Listening Plan, A-0049 Onboarding Question Set, A-0050 "What I Can Offer This Week" One-Pager). Add a kit master index (`FIRST_WEEK_READINESS_KIT.md`) and a utility AI Integration Discussion Guide tracked in the kit index, not the backlog. Each artifact cites the Phase 3 governance envelope by filename and references W-15 as the operating workflow. No new backlog rows; six existing rows flipped to `Ready for personal use`. Phase 7 (Synthetic Demo Pack) is next.

## Source-of-truth review

Confirm:

- [x] Read `00_MASTER_CONTEXT/MASTER_CONTEXT.md` at session start.
- [x] Read the previous `09_HANDOFFS/SESSION_HANDOFF.md` at session start.
- [x] Working directory confirmed as `C:\Users\thalf\OneDrive\Documents\ATLAS-PM-Ops-OS`.
- [x] Phase prompt `05_PROMPTS/PHASE_PROMPTS/PHASE_06_FIRST_WEEK_READINESS_KIT.md` consulted.
- [x] W-15 (`04_WORKFLOWS/W-15-clearance-limited-onboarding.md`) re-read; the kit inherits its governance envelope and operating-workflow pattern.
- [x] Phase 3 governance bundle (`DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`, `AI_CONVERSATION_GUIDE.md`, `EMPLOYER_TOOL_APPROVAL_QUESTION_SET.md`) re-read to confirm citation pattern.
- [x] Existing seeded `07_TEMPLATES/FIRST_WEEK_DISCOVERY_SCRIPT.md` and `07_TEMPLATES/EXECUTIVE_NARRATIVE.md` re-read before hardening.

## Files changed

| Path | Type of change | Summary |
|---|---|---|
| `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md` | added | Kit master index: purpose, governance envelope citation, use posture, kit index table, universal kit rules, 14-bucket coverage map naming where each Phase 6 prompt bucket lives, maintenance notes, cross-references. |
| `07_TEMPLATES/FIRST_WEEK_DISCOVERY_SCRIPT.md` | updated | Hardened A-0005: added artifact identity header, governance envelope, use posture, first-manager-1:1 questions, stakeholder listening-tour questions, knowledge-management/Workspace questions, expanded AI workflow discovery questions, clearance-limited contribution options, things-not-to-do-in-week-one list, end-of-week summary template, end-of-week reflection prompts, cross-references. |
| `07_TEMPLATES/EXECUTIVE_NARRATIVE.md` | updated | Hardened A-0006: added artifact identity header, governance envelope, PM/Ops + AI integration positioning paragraph, explicit forward-looking marker, reviewer sign-off line, narrative quality checklist, failure modes, migration notes, cross-references to W-12 / P-12 / P-99 / P-00. |
| `07_TEMPLATES/CLEARANCE_LIMITED_VALUE_PLAN.md` | added | A-0022 Clearance-Limited Value Plan: eight value categories (ATLAS hardening, public study, synthetic-demo refinement, listening-tour prep, process-gap notes, SOP first drafts, executive-narrative practice, governance familiarity), visible-artifact discipline, do-not-promise list, end-of-week reflection. |
| `07_TEMPLATES/LISTENING_PLAN.md` | added | A-0048 Listening Plan: daily-entry shape, what-to-capture vs what-not-to-capture lists, sanitization filter (six-question gate), weekly Friday reflection. Pairs with future W-16. |
| `07_TEMPLATES/ONBOARDING_QUESTION_SET.md` | added | A-0049 Onboarding Question Set: six audience-split banks (manager, peers, IT, security, compliance, program leadership) with venue / rapport / clearance markers, tailoring discipline, cross-references to `06_GOVERNANCE/EMPLOYER_TOOL_APPROVAL_QUESTION_SET.md`. |
| `07_TEMPLATES/WHAT_I_CAN_OFFER_THIS_WEEK.md` | added | A-0050 "What I Can Offer This Week" one-pager: template with commitments / not-committing-to / AI posture / question-for-manager / sign-off, drafting checklist, red flags mirroring W-15 §11, escalation triggers mirroring W-15 §13, migration notes. Scope rule logged as D-0044. |
| `07_TEMPLATES/AI_INTEGRATION_DISCUSSION_GUIDE.md` | added | Utility template (kit-index-tracked per D-0043): Tom's framing for AI questions, what-to-bring / what-not-to-bring lists, conversational openers, audience-by-audience talking points, synthetic-demo usage rules, drift recovery moves, post-conversation capture rules. Parent reference: `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md`. |
| `03_BACKLOG/ARTIFACT_BACKLOG.md` | updated | Six first-week-readiness rows (A-0005, A-0006, A-0022, A-0048, A-0049, A-0050) flipped from `Seeded` / `Not started` to `Ready for personal use` with Notes columns pointing at the kit file paths and the kit index. "Current build recommendation" tail rewritten to mark Phase 6 complete and name Phase 7 as next, carrying forward A-0038 and A-0029 as optional housekeeping. |
| `10_DECISION_LOG/DECISION_LOG.md` | updated | Appended D-0040..D-0044 covering the Phase 6 branch deviation, the kit hybrid layout, the governance-envelope citation discipline, the utility-template status of the AI Integration Discussion Guide, and the scoping rule for the manager-shared one-pager. |
| `00_MASTER_CONTEXT/MASTER_CONTEXT.md` | updated | Bumped current build stage to "Phase 6 - First-Week Readiness Kit (complete)" and rewrote "Immediate objective" to describe the eight-file kit and name Phase 7 (Synthetic Demo Pack) as the next objective. |

## Completed work

- Authored `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md` as the kit master index with a 14-bucket coverage map showing exactly which sub-file covers each Phase 6 prompt bucket.
- Hardened `07_TEMPLATES/FIRST_WEEK_DISCOVERY_SCRIPT.md` (A-0005): added the governance envelope, W-15 reference, first-manager-1:1 questions, stakeholder listening-tour questions, knowledge-management / Workspace questions, expanded AI workflow discovery questions, clearance-limited contribution options, a things-not-to-do-in-week-one list, and an end-of-week summary template. Preserved the original opening positioning and the existing five domain question sets.
- Hardened `07_TEMPLATES/EXECUTIVE_NARRATIVE.md` (A-0006): added the governance envelope, the PM/Ops + AI integration positioning paragraph, explicit forward-looking marker in the template, reviewer sign-off line, failure modes, and migration notes. Preserved the existing seven-section narrative template; tightened the use rules.
- Authored `07_TEMPLATES/CLEARANCE_LIMITED_VALUE_PLAN.md` (A-0022) with eight value categories and a do-not-promise list mirroring the W-15 §11 red flags.
- Authored `07_TEMPLATES/LISTENING_PLAN.md` (A-0048) with a sanitization filter that prevents restricted content from entering ATLAS or Tom-personal notes.
- Authored `07_TEMPLATES/ONBOARDING_QUESTION_SET.md` (A-0049) with six audience-split banks (manager / peers / IT / security / compliance / program leadership), each tagged for venue / rapport / clearance state.
- Authored `07_TEMPLATES/WHAT_I_CAN_OFFER_THIS_WEEK.md` (A-0050) with a drafting checklist and red-flag list that explicitly mirror W-15 §11 and §13.
- Authored `07_TEMPLATES/AI_INTEGRATION_DISCUSSION_GUIDE.md` as a kit-layer companion to `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md`; tracked in the kit master index per D-0043, not the backlog.
- Reconciled `03_BACKLOG/ARTIFACT_BACKLOG.md`: six status flips, six Notes updates, "Current build recommendation" rewritten.
- Logged five Phase 6 decisions in `10_DECISION_LOG/DECISION_LOG.md` (D-0040..D-0044) in the same session.
- Updated `00_MASTER_CONTEXT/MASTER_CONTEXT.md` to mark Phase 6 complete and name Phase 7 as the next objective.
- Worked Phase 6 on branch `claude/atlas-pm-ops-phase-OhdyH` (deviation from the `feat/phase-NN-<slug>` convention is documented in D-0040, parallel to D-0033 for Phase 4 and D-0039 for Phase 5).

## Decisions made

| Decision | Rationale | File or area impacted |
|---|---|---|
| Perform Phase 6 on the constrained branch `claude/atlas-pm-ops-phase-OhdyH`. CLAUDE.md commit and branch policy otherwise applies. | Branch was created by the operating environment before the session began; parallel to D-0033 and D-0039. The deviation is narrow, not a precedent. | Git. |
| Structure Phase 6 as a hybrid: kit master index + six backlog-row files + one utility template under `07_TEMPLATES/`. | Per-artifact files parallel the Phase 4 (D-0031) and Phase 5 (D-0037) hybrids, give Codex per-line review precision, and let each artifact name a visible-artifact contract. | `07_TEMPLATES/` layout. |
| Each kit file cites the Phase 3 governance envelope by filename and references W-15 as the operating workflow; no policy is restated at the kit-artifact layer. | Mirrors the Phase 4 §4 / Phase 5 §3 envelope discipline (D-0029, D-0036); citing rather than restating prevents drift across the seven kit files. | All `07_TEMPLATES/` Phase 6 files. |
| The AI Integration Discussion Guide is a utility template tracked in the kit master index, not the backlog. It cites `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md` as the parent reference and does not restate it. | The Phase 6 prompt names the guide as a deliverable but no backlog row exists; tracking it in the kit index parallels the P-00 / P-99 utility-prompt pattern (D-0038). | `07_TEMPLATES/AI_INTEGRATION_DISCUSSION_GUIDE.md` and the kit index. |
| The "What I Can Offer This Week" one-pager must not commit to scope outside the manager-agreed clearance-limited posture; red flags mirror W-15 §11 and escalation triggers mirror W-15 §13. | The one-pager is the kit artifact most at risk of overclaim drift; naming the scoping rule at the decision-log layer keeps it authoritative across future edits and review rounds. | `07_TEMPLATES/WHAT_I_CAN_OFFER_THIS_WEEK.md`. |

These decisions are logged in this session as `D-0040` through `D-0044` in `10_DECISION_LOG/DECISION_LOG.md`, in the same order as the table above.

## Safety review

Confirm:

- [x] No real employer data used.
- [x] No classified data used.
- [x] No CUI used.
- [x] No ITAR or export-controlled data used.
- [x] No proprietary, customer, contract, internal schedule, internal finance, or internal technical data used.
- [x] No real program names, real meeting notes, real Microsoft Project files, or real project accounting exports used.
- [x] All examples are synthetic, public, generic, fictional, or Tom-personal. Every template uses placeholders (`[YYYY-MM-DD]`, `[Synthetic placeholder]`, `[Name/role]`, `[Manager's name and role]`, `[Verb-led commitment]`, `[Date range]`, `[Confirmed fact 1..3]`, `[Schedule implication, if known]`, `[Cost/resource implication, if known]`, `[Description]`, `[Owner or TBD]`, `[Next action]`, `[Forecast or projection]`, `[Action] — Owner — Due`, `[Question or assumption]`, `[Adjustments after review]`).
- [x] Human-in-the-loop posture preserved: every kit artifact names the named human reviewer (Tom for daily practice, manager for the weekly one-pager), cites the per-domain review pattern, and forbids AI from deciding, approving, sending, or committing.
- [x] Gemini-first and platform-agnostic posture preserved: kit artifacts use generic "AI assistant" framing and `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md`'s tool-agnostic talking points; no Gemini-specific syntax assumed.
- [x] No app, package, API, database, deployment, or code scaffolding added.

## Definition-of-done check

Confirm:

- [x] Every artifact created or updated is Markdown-first and portable.
- [x] Every artifact has a clear purpose and an obvious human review step where relevant (Tom for personal practice; manager for the weekly one-pager).
- [x] No artifact assumes access or data Tom may not have during clearance-limited onboarding. The do-not-promise list in `CLEARANCE_LIMITED_VALUE_PLAN.md` and the red flags in `WHAT_I_CAN_OFFER_THIS_WEEK.md` make this explicit.
- [x] This handoff file is up to date and contains the next best prompt.
- [x] Significant decisions from this session are logged in `10_DECISION_LOG/DECISION_LOG.md` in this same session (entries `D-0040` through `D-0044`); none deferred.
- [x] Mode-gated commit step from the session-end protocol is satisfied: local-agent mode commits Phase 6 changes on branch `claude/atlas-pm-ops-phase-OhdyH` in small Conventional Commits and opens a PR against `main` at session end.

## Open items

- A-0038 Process Gap Note Workflow remains `Not started` (carried from Phase 4). It pairs naturally with the Phase 6 listening plan (`LISTENING_PLAN.md`); build as `W-16-process-gap-note.md` either during Phase 7 or as a short follow-up session.
- A-0029 Local skill files refresh remains `Not started`. The Phase 4 / 5 / 6 patterns are now stable; the three `skills/*/SKILL.md` files can be reviewed against the combined workflow + prompt + kit schemas. Pair with the Phase 7 build or a chore branch.
- The kit's listening plan and clearance-limited value plan reference the future `04_WORKFLOWS/W-16-process-gap-note.md`. The cross-reference is fine while W-16 is unbuilt; when W-16 lands, update both files' cross-reference sections in the same session.
- Phase 7 demos will exercise the Phase 4 W-NN cards and Phase 5 P-NN paired prompts end-to-end. The Phase 6 kit assumes a Phase 7 demo pack will exist; the discussion guide and value plan reference `08_SYNTHETIC_DEMOS/` content even though most rows in that folder are not yet built. This is by design - the references will resolve as Phase 7 lands.

## Risks and cautions

- The First-Week Readiness Kit is conservative on purpose. Several artifacts (notably the one-pager and the value plan) explicitly limit scope to personal-preparation work and forbid commitments that depend on cleared access; that is the intended posture, not a gap. Future review feedback that tries to broaden the kit into employer-deployable scope should be redirected to Phase 11 (Employer Migration).
- The listening plan's six-question sanitization filter is the discipline gate. If a future entry would not survive the filter, the right move is to forget the entry for ATLAS purposes - not to soften the filter. Loosening the filter would require a new logged decision per D-0042's spirit.
- The "What I Can Offer This Week" one-pager is the kit artifact most exposed to overclaim drift. D-0044's scoping rule is the binding constraint; any review request to loosen it requires a new logged decision before being accepted.
- The AI Integration Discussion Guide is a kit-layer companion to `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md`, not a replacement. Edits that drift from the parent governance file should update the governance file first and then propagate to the kit guide through citation.

## AI tooling notes

The Phase 6 kit is authored Gemini-first and platform-agnostic. Personal AI tools (Claude, ChatGPT, Gemini consumer) are the default tool environment for personal-preparation use - on Synthetic / Public / Tom-personal inputs only. An Employer-approved AI tool only enters the picture once explicit approval exists for the specific data category, per the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`. Every kit artifact's governance envelope makes the data-category and tool-environment routing explicit. The AI Integration Discussion Guide's hard-do-not list is restated locally for kit-conversation use but is anchored to `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md` as the source of truth.

## Recommended next phase or artifact

**Phase 7: Synthetic Demo Pack**

Build fictional demonstrations that prove ATLAS workflow value without real employer data. Phase 7 exercises the Phase 4 W-NN workflow cards and the Phase 5 P-NN paired prompts end-to-end against synthetic inputs. Backlog rows: A-0007 (Synthetic Status Pack Demo, already Seeded) and not-started rows A-0023 (Synthetic Schedule Variance Demo), A-0024 (Synthetic Action Tracker Demo), A-0051 (Synthetic Discrepancy Triage Demo), A-0052 (Synthetic Risk Register Cleanup Demo). Each demo cites the Phase 3 governance envelope and the paired W-NN / P-NN pair by ID, walks input → AI step → human review → output as a pattern (not as a product), and is explicitly labeled synthetic. Demos must be safe to show in an early conversation with a manager or peer without ever blending in real data.

Optional housekeeping during or after Phase 7:

- Build A-0038 Process Gap Note as `04_WORKFLOWS/W-16-process-gap-note.md`. Pairs naturally with the Phase 6 listening plan.
- Refresh A-0029 local skill files (`skills/*/SKILL.md`) against the Phase 4 / 5 / 6 schemas.

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
6. 05_PROMPTS/PROMPT_LIBRARY.md
7. 06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md
8. 06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md
9. 06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md
10. 06_GOVERNANCE/AI_GOVERNANCE_NOTES.md
11. 07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md
12. 08_SYNTHETIC_DEMOS/SYNTHETIC_STATUS_PACK_DEMO.md
13. 05_PROMPTS/PHASE_PROMPTS/PHASE_07_SYNTHETIC_DEMO_PACK.md

Phase to run:
Phase 7: Synthetic Demo Pack

Phase prompt file:
05_PROMPTS/PHASE_PROMPTS/PHASE_07_SYNTHETIC_DEMO_PACK.md

Safety boundary (one line):
Use only synthetic, public, generic, fictional, or user-created non-proprietary material. Do not use classified, CUI, ITAR/export-controlled, proprietary, customer, contract, internal schedule, internal finance, internal technical, real meeting note, real Microsoft Project, or real accounting data.

Posture:
Markdown-first, Gemini-first, platform-agnostic, human-in-the-loop, approved-tool-first. Do not add apps, package dependencies, APIs, databases, deployment files, or code scaffolding. Build the synthetic demo pack under 08_SYNTHETIC_DEMOS/ so each demo exercises a Phase 4 W-NN workflow card paired with the matching Phase 5 P-NN prompt end-to-end on fictional input. Demos must be labeled synthetic at the top, walk input → AI step → human review → output as a pattern, never blend in real data, and never claim deployment-readiness. Cover the seeded A-0007 (Synthetic Status Pack Demo, already at 08_SYNTHETIC_DEMOS/SYNTHETIC_STATUS_PACK_DEMO.md - harden if needed) and the not-started rows A-0023 (Synthetic Schedule Variance Demo, pair with W-05 / P-05), A-0024 (Synthetic Action Tracker Demo, pair with W-02 / P-02 and W-03 / P-03), A-0051 (Synthetic Discrepancy Triage Demo, pair with W-08 / P-08), A-0052 (Synthetic Risk Register Cleanup Demo, pair with W-07 / P-07). Each demo cites the Phase 3 governance envelope by name (data category Synthetic; tool environment ATLAS-local Markdown with Personal AI tool acceptable; review intensity Light for synthetic practice; per-domain review pattern matched to the demo). Log Phase 7 decisions in 10_DECISION_LOG/DECISION_LOG.md in the same session. Update 09_HANDOFFS/SESSION_HANDOFF.md at the end with the Phase 8 next best prompt. Optional housekeeping: build A-0038 Process Gap Note Workflow as 04_WORKFLOWS/W-16-process-gap-note.md (paired Phase 5 prompt: none expected; it is a personal-note workflow), and refresh A-0029 local skill files against the Phase 4 / 5 / 6 schemas.
```
