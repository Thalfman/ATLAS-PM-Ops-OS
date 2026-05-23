# LISTENING_PLAN.md

## Artifact identity

- **Backlog ID:** A-0048
- **Phase:** 6 - First-Week Readiness Kit
- **Operating workflow:** `04_WORKFLOWS/W-15-clearance-limited-onboarding.md`
- **Kit index:** `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

Structure how Tom listens during clearance-limited onboarding for process gaps, reporting friction, action-tracking issues, and AI-adjacent pain points - without paraphrasing restricted content into personal notes or ATLAS. Pairs with the future `04_WORKFLOWS/W-16-process-gap-note.md` (A-0038) when that is built.

## Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Tom-personal. Generic process observations only; never paraphrased restricted content.
- **Tool environment** (same file, "Tool environments"): ATLAS-local Markdown for generic-enough entries. Tom-personal notes (outside ATLAS) for anything that would be hard to fully sanitize.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Light. Tom self-reviews end-of-day.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Status and reporting outputs.

## Use posture

- Listen before forming opinions.
- Observe shape; do not record content.
- Capture in neutral, generic language - the entry should make sense to a reader who has no context on the program.
- Daily cadence: a short entry at the end of each working day; weekly reflection on Fridays.
- If an entry cannot be written without restricted content, do not write it.

## Daily entry structure

Each end-of-day entry uses this short shape:

```text
Date: [YYYY-MM-DD]
Observation type: [Process | Reporting | Action tracking | AI-adjacent | Other]
What I observed (generic): [One or two sentences, no program/customer/contract specifics, no real names, no real numbers.]
Why it matters: [One sentence on the PM/Ops or reporting consequence, in the abstract.]
Possible improvement (do not raise yet): [One sentence, named at the process level, not at the person level.]
Confidence: [Tentative | Reasonably sure | Confirmed by independent observation]
Carry forward? [Yes / No / Watch for one more week]
```

Five to seven lines per entry is plenty. The plan succeeds by being sustainable, not exhaustive.

## What to capture

Generic, process-level observations such as:

- Reporting cadence mismatches (e.g., "the weekly report relies on inputs that arrive after the cutoff").
- Tool friction in the abstract (e.g., "the schedule narrative is hand-assembled from multiple views; no single source of truth").
- Action-item drift (e.g., "actions captured in meeting notes often lose their owner before the next meeting").
- Reconciliation pain points (e.g., "labor hours and EVM updates are reconciled by manual cross-check").
- Governance friction (e.g., "the AI tool approval process is not visible to the average PM").
- Knowledge-management friction (e.g., "templates live in multiple Drive locations; SOPs are not centrally indexed").

## What not to capture

Do not capture:

- Real program names, customer names, contract numbers, classified or CUI references, or any export-controlled detail.
- Real meeting content - what specific people said, agreed to, or pushed back on.
- Real schedule, finance, or EVM numbers; real activity IDs; real account codes.
- Real document filenames if those names would reveal program or customer detail.
- Anything overheard in a restricted area or briefing.
- Anything Tom would not be comfortable showing to an auditor as a personal preparation note.

If an observation is interesting but cannot be generalized safely, the right move is to forget it for ATLAS purposes. Personal recall is fine; written paraphrase is not.

## Sanitization filter (run before saving each entry)

Before saving any entry to ATLAS or to Tom-personal notes, run the following one-by-one. If any answer is "yes," rewrite or drop the entry.

1. Does the entry name a real program, customer, contract, or product?
2. Does the entry quote, paraphrase, or imply restricted briefing content?
3. Could a reader inside the company identify the specific situation from the entry?
4. Does the entry include a real number, percentage, date, or identifier that ties to a real program?
5. Does the entry name a specific individual or team in a way that could be read as criticism?
6. Could the entry be embarrassing if it were read out loud in a manager's office?

Default: when in doubt, do not save the entry. The plan is more useful with 10 honest generic entries than with 50 detailed entries that violate the boundary.

## Weekly reflection (Friday)

At the end of each week, in a `## Week of YYYY-MM-DD` section under the daily entries:

- Three to five themes that surfaced across the week's entries.
- One theme Tom could raise constructively at the next manager 1:1 (named at the process level, not at the person level).
- One theme worth carrying into next week's observation (watch for one more week before raising).
- Any entry that drifted into restricted territory mid-week - mark for deletion, then delete.

## Cross-references

- Operating workflow: `04_WORKFLOWS/W-15-clearance-limited-onboarding.md` (§10 step 5 "Maintain the listening log").
- Kit index: `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`.
- Future workflow pair: `04_WORKFLOWS/W-16-process-gap-note.md` (A-0038, not yet built).
- One-pager for the manager: `07_TEMPLATES/WHAT_I_CAN_OFFER_THIS_WEEK.md`.
- Onboarding question set: `07_TEMPLATES/ONBOARDING_QUESTION_SET.md` (translates safe observations into questions worth asking).
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0048.
