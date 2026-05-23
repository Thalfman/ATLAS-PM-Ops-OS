# CLEARANCE_LIMITED_VALUE_PLAN.md

## Artifact identity

- **Backlog ID:** A-0022
- **Phase:** 6 - First-Week Readiness Kit
- **Operating workflow:** `04_WORKFLOWS/W-15-clearance-limited-onboarding.md`
- **Kit index:** `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A conservative menu of valuable work Tom can do during clearance-limited onboarding without touching restricted content. Each item names a visible artifact and a target cadence so Tom and the manager can agree on the week's commitments. Pairs with `WHAT_I_CAN_OFFER_THIS_WEEK.md` for the manager-shared one-pager.

## Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Tom-personal. Public when based on public material. Synthetic when refining ATLAS demo content. Never Employer-approved while clearance is pending.
- **Tool environment** (same file, "Tool environments"): ATLAS-local Markdown. Personal AI tool acceptable on Synthetic / Public / Tom-personal inputs only.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Light for personal practice; Standard for any item shared with the manager.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Status and reporting outputs.

## Use posture

- Listen first, propose second.
- Never promise an outcome that depends on cleared access.
- Every commitment names a visible artifact (a file path, a note, a study log entry, a demo refinement).
- Cadence is honest: a week's plan must fit a week's available time, accounting for orientation, paperwork, and training.

## Value categories Tom can offer during clearance-limited onboarding

The categories below are sources of value. They are not commitments. Tom picks 3-5 each week and turns them into the manager-shared one-pager.

### 1. ATLAS hardening and refinement (Synthetic)

- Review one phase folder (`02_ROADMAP/`, `04_WORKFLOWS/`, `05_PROMPTS/`, `06_GOVERNANCE/`, etc.) and tighten one artifact per session.
- Strengthen a synthetic workflow card based on what Tom observes about general PM/Ops process shape in the new environment - without naming any specific program or process Tom is not authorized to discuss.
- Visible artifact: a commit on a feature branch with a Conventional Commits message and a short summary in `09_HANDOFFS/SESSION_HANDOFF.md`.

### 2. Public PM/Ops and AI study (Public)

- Read one PMI, PMBOK, EVM, schedule-integrity, or project-controls article per day.
- Read one public Responsible AI piece per day (NIST AI RMF, public AI governance frameworks, vendor-published responsible-AI material).
- Capture a 3-5 line study note per item under Tom's personal preparation notes; if the note is generic enough to live in ATLAS, commit it.
- Visible artifact: a dated study log in Tom-personal notes or a `notes/` subfolder in ATLAS.

### 3. Synthetic demo refinement (Synthetic)

- Pick one Phase 5 paired prompt and walk it end-to-end against the matching synthetic demo input. Improve the prompt's failure-mode list, the trace appendix, or the placeholder set.
- Improve one synthetic demo under `08_SYNTHETIC_DEMOS/` (when that phase is built) so the input-to-output trace is cleaner.
- Visible artifact: a diff on the prompt card or the synthetic demo, plus a 2-3 line note in `09_HANDOFFS/SESSION_HANDOFF.md`.

### 4. Listening tour preparation (Tom-personal)

- Tailor `07_TEMPLATES/ONBOARDING_QUESTION_SET.md` for the next scheduled conversation (manager 1:1, peer intro, IT, security, compliance, program lead).
- Update `07_TEMPLATES/LISTENING_PLAN.md` end-of-day reflections in neutral language.
- Visible artifact: the tailored question set saved as a personal note (not in ATLAS unless generic); the listening plan entry in ATLAS (only generic content).

### 5. Process gap notes (Tom-personal)

- Capture observed process or reporting friction in neutral language - no restricted content, no real program names. Use the future `04_WORKFLOWS/W-16-process-gap-note.md` pattern when it exists (A-0038); until then, a 5-line note pattern: observation, why it matters, generic improvement idea, who would own it, ATLAS workflow it might pair with.
- Visible artifact: a personal note Tom may later raise with his manager when appropriate.

### 6. SOP first drafts from public material (Public / Synthetic)

- Drafting an SOP from a public PMI process description or a synthetic ATLAS workflow card, using `05_PROMPTS/P-11-sop-first-draft.md` against the synthetic input.
- Visible artifact: a draft SOP in `08_SYNTHETIC_DEMOS/` (or Tom-personal notes); never a real SOP for a real program.

### 7. Executive narrative practice (Synthetic)

- Practice the executive narrative template (`07_TEMPLATES/EXECUTIVE_NARRATIVE.md`) against a synthetic scenario using `05_PROMPTS/P-12-executive-brief-drafting.md`. Run the P-99 critique pass.
- Visible artifact: a dated practice narrative in Tom-personal notes; reviewed for clarity, not for any real program.

### 8. Governance familiarity (Public / Tom-personal)

- Re-read one `06_GOVERNANCE/` file per session and identify one place where the file would benefit from a clarification - without referencing employer-specific facts.
- Prepare to discuss the personal-preparation vs employer-deployable distinction (D-0026) in any AI integration conversation.
- Visible artifact: a 2-3 line note on the file or a minor doc-only PR.

## Visible-artifact discipline

Each weekly commitment is selected from the categories above and stated in this shape:

```text
- [Verb-led commitment] - Artifact: [path or note] - By: [date or end-of-week]
```

Examples (synthetic, illustrative only):

```text
- Strengthen the failure-modes list in `05_PROMPTS/P-05-schedule-variance-narrative.md` against the synthetic schedule demo. Artifact: PR diff on feature branch. By: end of Friday.
- Study the public NIST AI RMF executive summary and capture five PM/Ops-relevant principles. Artifact: study note in personal notes. By: Wednesday.
- Tailor `07_TEMPLATES/ONBOARDING_QUESTION_SET.md` for the IT 1:1. Artifact: personal note with the trimmed question list. By: 24 hours before the meeting.
```

## Do-not-promise list

Any of the following commitments are out of bounds during clearance-limited onboarding and must not appear on the weekly one-pager:

- Anything that requires access to a cleared workstream, classified workspace, customer-specific content, contract content, or restricted program detail.
- Anything that depends on real Microsoft Project files, real finance/EVM data, real schedules, real meeting notes, or real reports.
- Any AI workflow against employer data, even via an approved tool, until the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md` is walked for that specific use case and explicit approval exists.
- Any commitment that implies Tom has authority over policy, tools, or scope he has not been granted.
- Anything that would require shadow IT, personal-account workarounds, or unsanctioned data movement.
- Vague commitments without a visible artifact ("learn more about X," "explore Y") - convert to a concrete artifact or drop.

## End-of-week reflection

At the end of each clearance-limited week, capture in `07_TEMPLATES/LISTENING_PLAN.md` (or Tom-personal notes when generic enough is not possible):

- Which commitments were delivered; for each, the artifact path.
- Which commitments slipped, and why (real cause, not a polished excuse).
- One observation about the operating rhythm that is safe to raise with the manager next week.
- One question to bring to the next manager 1:1.

## Cross-references

- Operating workflow: `04_WORKFLOWS/W-15-clearance-limited-onboarding.md` (§7 weekly plan output; §10 step-by-step).
- Kit index: `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`.
- One-pager that Tom shares with the manager: `07_TEMPLATES/WHAT_I_CAN_OFFER_THIS_WEEK.md`.
- Listening plan: `07_TEMPLATES/LISTENING_PLAN.md`.
- Onboarding question set: `07_TEMPLATES/ONBOARDING_QUESTION_SET.md`.
- AI integration discussion guide: `07_TEMPLATES/AI_INTEGRATION_DISCUSSION_GUIDE.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0022.
- Decision log: D-0040..D-0044 (Phase 6 set).
