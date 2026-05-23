# SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md

**SYNTHETIC DEMO. FICTIONAL SCHEDULE. NOT MOTOROLA SOLUTIONS, NOT ANY REAL PROGRAM, CUSTOMER, OR CONTRACT.**

## Artifact identity

- **Backlog ID:** A-0023
- **Phase:** 7 - Synthetic Demo Pack
- **Paired workflow card:** `04_WORKFLOWS/W-05-schedule-variance-narrative.md`
- **Paired prompt card:** `05_PROMPTS/P-05-schedule-variance-narrative.md`
- **Shared scenario:** `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`
- **Pack index:** `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Governance envelope

- **Data category:** Synthetic.
- **Tool environment:** ATLAS-local Markdown; Personal AI tool acceptable for the AI-step exercise.
- **Review intensity:** Light for personal practice.
- **Per-domain review pattern:** Schedule outputs (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`).

Full citation pattern inherited from `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md` and the paired `W-05` card §4.

## Demo purpose

Walk a schedule variance narrative end-to-end: a fictional baseline-vs-current schedule delta on Project Northstar Demo, an AI-drafting step using P-05, a human-review pass following the "Schedule outputs" pattern, and a final narrative that frames causes as observations not conclusions.

## Step 1 - Synthetic input

The Project Northstar Demo schedule snapshot, taken at the close of week 2 (2026-05-15).

| Activity ID | Activity | Baseline start | Baseline finish | Current start | Current finish | Variance (finish, days) | Critical path? |
|---|---|---:|---:|---:|---:|---:|---|
| NS-A-01 | Draft weekly status template | 2026-05-04 | 2026-05-08 | 2026-05-04 | 2026-05-08 | 0 | Yes |
| NS-A-02 | Stakeholder review of template | 2026-05-11 | 2026-05-13 | 2026-05-11 | 2026-05-13 | 0 | Yes |
| NS-B-01 | Build action tracker prototype | 2026-05-11 | 2026-05-15 | 2026-05-12 | 2026-05-17 | +2 | Yes |
| NS-B-02 | Confirm action owners across team | 2026-05-15 | 2026-05-15 | 2026-05-17 | 2026-05-19 | +4 | No |
| NS-C-01 | Schedule risk-review workshop | 2026-05-18 | 2026-05-20 | 2026-05-18 | 2026-05-20 | 0 | Yes |
| NS-C-02 | Lessons learned first draft | 2026-05-20 | 2026-05-22 | 2026-05-22 | 2026-05-24 | +2 | No |
| NS-A-03 | Reporting pack pilot run | 2026-05-25 | 2026-05-29 | 2026-05-27 | 2026-06-02 | +4 | Yes |

Critical-path observation: the two-day slip on NS-B-01 propagated through NS-B-02 (owner confirmation depends on the tracker existing) and into NS-A-03 (pack pilot needs working tracker inputs).

## Step 2 - AI step (P-05 invocation pattern)

Tom runs `P-00-safety-precheck.md` first: data category Synthetic, environment Personal AI tool, named reviewer Tom, paired workflow W-05. All clear.

Tom then sends the synthetic schedule snapshot above into a Personal AI tool with the `P-05-schedule-variance-narrative.md` copy-paste prompt text, filling placeholders:

- `[SYNTHETIC_PROJECT_NAME]` → Project Northstar Demo
- `[SYNTHETIC_PERIOD]` → 2026-05-04 through 2026-05-15
- `[FICTIONAL_VARIANCE]` → +2 to +4 day finish variances on NS-B-01, NS-B-02, NS-C-02, NS-A-03
- `[PAIRED_W_ID]` → W-05

## Step 3 - AI draft (before review)

```text
Variance summary
Project Northstar Demo shows finish-date variances ranging from +2 to +4 days across four activities at the week-2 cutoff. The critical path carries a +4 day slip into the reporting pack pilot (NS-A-03). Two off-critical activities also moved +2 to +4 days.

What moved
- NS-B-01 (Build action tracker prototype) finished two days late (baseline 2026-05-15, current 2026-05-17).
- NS-B-02 (Confirm action owners across team) finished four days late (baseline 2026-05-15, current 2026-05-19).
- NS-C-02 (Lessons learned first draft) finished two days late (baseline 2026-05-22, current 2026-05-24).
- NS-A-03 (Reporting pack pilot run) finished four days late (baseline 2026-05-29, current 2026-06-02), driven by upstream slip.

Apparent cause
- The schedule shows NS-B-01 starting one day after planned start, then taking the planned duration; the slip is at the front of that activity, not in its execution.
- NS-B-02 starts two days after NS-B-01 finished, which is consistent with owner-availability dependency rather than an execution problem.
- NS-A-03's slip is fully consistent with the propagation from NS-B-01 → NS-B-02 → pack pilot inputs; no independent driver visible.

Recovery posture
- Schedule shows NS-A-03 planned to recover by the M-05 target (2026-05-29 → 2026-06-02 current); planned mitigation not yet captured in the schedule.
- Named owner for recovery actions: PM/Ops for the tracker and pack pilot; Team Lead for owner-confirmation cadence.

Decisions or inputs needed
- Whether to accept the +4 day finish on NS-A-03 against the M-05 milestone, or re-plan the pack pilot to recover the original date.
- Whether to convert the owner-confirmation slip into a process change (require owner / due-date confirmation before meeting close) per the existing risk R-001 mitigation.
```

## Step 4 - Human review (Schedule outputs pattern)

Per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Schedule outputs":

- **Recompute numeric claims.** NS-B-01 +2, NS-B-02 +4, NS-C-02 +2, NS-A-03 +4 — match the input table. Pass.
- **Confirm narrative matches the data.** The AI's "schedule shows NS-B-01 starting one day after planned start" is consistent with the baseline 2026-05-11 vs current 2026-05-12 start. Pass.
- **Confirm activity names and IDs match the source.** All seven activity IDs (NS-A-01..03, NS-B-01..02, NS-C-01..02) match the input. Pass.
- **Confirm no over-attribution of causes.** AI framed causes as observations ("schedule shows X starting N days after planned start") not conclusions ("Team Y delayed"). Pass.
- **Confirm no committed recovery dates the schedule does not support.** AI says "planned mitigation not yet captured in the schedule" rather than asserting a recovery date. Pass.

One edit Tom would make in practice: tighten "Recovery posture" to a single sentence per activity and label the M-05 trade clearly as a decision needed.

## Step 5 - Final narrative (after review)

Identical to the AI draft above with one wording change in §Recovery posture: "Schedule shows NS-A-03 planned finish at 2026-06-02; no recovery activities are yet captured in the schedule. PM/Ops to confirm whether to accept the +4 day finish or re-plan the pack pilot with the Team Lead." Reviewer sign-off line appended below for synthetic practice:

```text
Drafted by Tom on 2026-05-23 (synthetic practice).
Reviewed by Tom on 2026-05-23 (Light intensity, synthetic input).
Adjustments after review: tightened recovery posture per "Schedule outputs" pattern.
```

## Demo value

This demo illustrates that the AI step is a structuring and drafting move, not an analytical conclusion. Numbers were already in the schedule; the AI's contribution is the narrative shape (variance summary → what moved → apparent cause as observation → recovery posture → decisions needed). Tom's review confirms the numbers, the causal framing, and the decision callout. Migration to real schedule data requires re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md` and routing to an Employer-approved AI tool with explicit scope approval (W-05 §14).

## Cross-references

- Paired workflow card: `04_WORKFLOWS/W-05-schedule-variance-narrative.md` (§7 output format, §9 review point, §11 quality checks).
- Paired prompt card: `05_PROMPTS/P-05-schedule-variance-narrative.md`.
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Shared scenario: `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.
- Pack index: `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0023.
