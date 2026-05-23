# P-08-issue-and-discrepancy-triage - Issue and discrepancy triage

## Prompt identity

- **ID:** P-08
- **Paired workflow:** W-08 (`04_WORKFLOWS/W-08-issue-and-discrepancy-triage.md`)
- **Backlog ID:** A-0043
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Convert a raw issue or discrepancy list into a triage table with one-line descriptions, severity, affected scope, next step, target date, status, and notes — plus investigation candidates and an open-ownership list. The prompt addresses W-08 §2: issues that get described but never converted into a trackable resolution path. The deliverable is the table and the three sub-lists described in W-08 §7.

## 2. Paired workflow and PM/Ops role

Paired with `W-08-issue-and-discrepancy-triage.md`. Executes steps 4-5 of the W-08 §10 process: convert raw issues to triage rows, propose investigation questions for ambiguous issues. AI role: structure, name blind spots, propose investigation questions. AI must not assign severity or owner (Tom does), propose conclusions, or send anything.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real issues are Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for issue content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Risk and issue triage outputs.

## 4. Safe input requirements

Mirror W-08 §5:

- Synthetic issue or discrepancy notes for a fictional project.
- Generic issue examples from public PMI or quality-management material.
- Tom's own notes from a public training or his own non-restricted observations.

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-08 §6:

- Real customer complaints, real audit findings, real contract disputes.
- Real personnel or performance issues.
- Issues that reveal restricted program structure, real systems, or financial impact.

## 6. Placeholders used

- `[SYNTHETIC_PROJECT_NAME]` — fictional project name.
- `[APPROVED_INPUT]` — the raw issue list block (issue or discrepancy descriptions in whatever form they arrived; include source — email, report, observation — when not sensitive).
- `[PLACEHOLDER_OWNER]` — fictional owner names that may appear in the source.

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional triage raw issues and discrepancies.

ROLE
- Convert raw issue descriptions into a triage table.
- Propose 2-3 investigation questions for ambiguous issues.
- Do not assign severity. Severity is set by Tom; the AI may suggest with a stated criterion.
- Do not assign owner. Owner is set by Tom; the AI may suggest from the source if present.
- Do not propose conclusions for ambiguous issues; propose investigation questions instead.
- Do not propose escalation; do not propose sending anything.

INPUTS
- Project: [SYNTHETIC_PROJECT_NAME]
- Raw issue list:
[APPROVED_INPUT]
- Known owners that may appear: [PLACEHOLDER_OWNER]

OUTPUT FORMAT

Return a Markdown triage table:

| # | One-line description | Severity (S1-S4) | Affected scope | Owner | Next step | Target date | Status (open / in progress / blocked / closed) | Notes |
|---|---|---|---|---|---|---|---|---|

Then, below the table:

**Severity definitions** (one line each, restate verbatim):
- S1 = stops work
- S2 = degrades quality or schedule
- S3 = inconveniences
- S4 = informational

**Investigation candidates** — for each row whose next step is "investigate" rather than "fix," list 2-3 questions that would resolve the ambiguity. Do not propose answers.

**Open ownership** — list each row whose Owner is "missing field" so Tom can assign before the triage record is used.

DISCIPLINE
- Severity cell is "missing field — Tom to set" for every row. AI may add a one-line suggested severity with criterion in the Notes column ("suggested S2: degrades quality of the weekly status report").
- Owner cell is "missing field" unless the source explicitly names the owner. AI may add a one-line suggested owner from the source in the Notes column.
- Target date is "missing field" unless the source provides one. Do not invent.
- Status defaults to "open" unless the source records otherwise.
- Notes column references the source of the issue (email date, report section, observation date) when not sensitive.
- Each row is one issue. Do not conflate two distinct issues into one row.

Return the table, the four lists below it, and nothing else.
```

## 8. Expected output

A Markdown triage table with nine columns followed by four labeled lists (Severity definitions, Investigation candidates, Open ownership; plus the implicit Severity definitions list). Mirrors W-08 §7.

## 9. Human review checklist

The reviewer (Tom; affected-scope owner for employer-deployable runs) follows the "Risk and issue triage outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist before using the output:

- Confirm each entry has an owner (or "missing field" — never an AI assignment).
- Confirm severity matches judgment, not AI inference; Tom assigns with a stated criterion.
- Confirm the next step is actionable.
- Confirm investigation candidates are clearly separated from fix candidates.
- Confirm Notes column references the source of the issue.

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-08 §13):

- AI assigns severity without criterion or merges two distinct issues.
- Next step is verb-only ("address it") with no concrete action.
- Owner is assigned without confirmation.
- Triage record diverges from the source list between iterations.
- Closed issues lose the audit trail of how they were closed.

Escalation triggers:

- Issue crosses into safety, compliance, contract, or customer-facing territory — go to program lead.
- Issue requires authority Tom does not have — go to manager.
- Issue turns out to involve Prohibited content — stop, do not use AI; reclassify.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Synthetic issue list, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real issue list, Employer-approved AI tool against approved scope, Strict review, owner-confirmation step before the triage record is used in any official tracker, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums."
- **Re-approval triggers:** Including customer-facing or contract-bearing issues; broadening scope to root-cause analysis; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm the raw issue list does not contain real customer complaints, real audit findings, or real personnel-performance content for personal-preparation runs.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before any row is used in an official tracker. Required for Strict review intensity.

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-08-issue-and-discrepancy-triage.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0043.
- Related demo: A-0051 Synthetic Discrepancy Triage Demo (Phase 7).
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-07-risk-register-cleanup.md`, `P-03-action-aging-summary.md`.
