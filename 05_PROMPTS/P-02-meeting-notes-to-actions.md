# P-02-meeting-notes-to-actions - Meeting notes to actions

## Prompt identity

- **ID:** P-02
- **Paired workflow:** W-02 (`04_WORKFLOWS/W-02-meeting-notes-to-actions.md`)
- **Backlog ID:** A-0040
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Convert raw meeting notes into a deduplicated action table with owner, due date, action, dependency, status, and source line — one row per action that an attendee actually agreed to. The prompt addresses W-02 §2: meeting outcomes that remain buried in narrative notes and never become trackable owner/date/action records. The deliverable is the table described in W-02 §7 plus the open-questions / decisions / source-range list below it.

## 2. Paired workflow and PM/Ops role

Paired with `W-02-meeting-notes-to-actions.md`. Executes steps 3-4 of the W-02 §10 process: paste the meeting notes; ask AI to extract, not infer. AI role: extract actions, owners, dates, and dependencies from the source notes only. AI must not infer ownership, invent due dates to fill columns, or compress disagreement into a single agreed action.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice; Tom-personal for Tom's own notes from public or non-restricted meetings.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first). Employer-approved AI tool when the meeting itself is employer business and the tool is approved for that content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard by default. Light only for clearly fictional practice.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Meeting notes to action items.

## 4. Safe input requirements

Mirror W-02 §5:

- Fictional meeting notes authored by Tom for practice.
- Tom's own notes from public or non-restricted meetings (training sessions, vendor briefings, public conferences).
- Generic example notes from training material.

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-02 §6:

- Real internal meeting notes from employer business unless the meeting itself and the tool are both approved for the content.
- Notes that reference real program names, contract details, customer details, financials, or internal technical content without explicit approval.
- Notes that paraphrase restricted briefings (paraphrased restricted content is restricted content).

## 6. Placeholders used

- `[SYNTHETIC_MEETING_TITLE]` — fictional or public meeting title.
- `[SYNTHETIC_DATE]` — meeting date.
- `[APPROVED_INPUT]` — the raw meeting notes block (paste as-is; do not summarize before sending).
- `[PLACEHOLDER_OWNER]` — fictional or Tom-personal owner names that may appear in the notes.

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional convert meeting notes into a structured action table.

ROLE
- Extract actions explicitly named or clearly agreed in the source notes.
- Do not infer actions, owners, or due dates.
- Do not silently commit anyone to anything.
- Do not compress a disagreement into a single agreed action.

INPUTS
- Meeting: [SYNTHETIC_MEETING_TITLE] on [SYNTHETIC_DATE]
- Raw notes (full text, not summarized):
[APPROVED_INPUT]
- Known attendees and any agreed pre-meeting owners: [PLACEHOLDER_OWNER]

OUTPUT FORMAT

Return a Markdown table with these columns, one row per agreed action:

| # | Owner | Action (verb-led, one line) | Due date | Dependency | Status | Source line |
|---|---|---|---|---|---|---|

Then, below the table:

**Open questions** (0-3 bullets) — anything the notes could not resolve. Inferred or implied actions go here, not in the table.
**Decisions made** (0-3 bullets) — decisions the meeting captured but that are not themselves actions.
**Source range** — the section of the input notes the table was derived from (line numbers or paragraph references).

DISCIPLINE
- Every row's Source line column must quote (or cite line number of) the exact line in the source notes that authorizes the row.
- Owner = "missing field" if the notes do not name an owner; do not guess.
- Due date = "missing field" if the notes do not name a date; do not invent.
- Status = open by default, unless the notes record completion.
- If the same action is mentioned twice with conflicting owners or dates, create one row and add the conflict to Open questions; do not pick one.

Return the table, the three lists below it, and nothing else.
```

## 8. Expected output

A Markdown table with seven columns (#, Owner, Action, Due date, Dependency, Status, Source line) plus three sub-lists (Open questions, Decisions made, Source range). Mirrors W-02 §7.

## 9. Human review checklist

The reviewer (Tom) follows the "Meeting notes to action items" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist before using the output:

- Confirm every action has an owner and a date (or "missing field" — never an AI guess).
- Confirm the owner has actually been informed (the AI tool has not silently committed anyone).
- Confirm the action is what the owner actually agreed to, not what the AI inferred.
- Verify each row against the source line referenced in the last column.
- Confirm duplicates from the meeting are merged.

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-02 §13):

- AI invents an owner the notes do not name.
- AI invents a due date to satisfy the column.
- AI silently commits a person to an action they did not agree to.
- AI compresses a disagreement into a single action that hides the disagreement.
- Reviewer accepts the table without opening the source notes.

Escalation triggers:

- The notes themselves are ambiguous about who agreed to what — go to the attendees.
- An action would require Tom or another person to commit beyond their authority — go to manager.
- The notes turn out to contain restricted content — stop, do not use AI; reclassify.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Fictional or Tom-personal notes, Personal AI tool, Standard review, sign-off line in the output.
- **Employer-deployable form (after approval):** Real meeting notes from approved-content meetings, Employer-approved AI tool, Strict review, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums," owner-confirmation step per action before the row enters any official tracker.
- **Re-approval triggers:** New meeting category (e.g., contract-bearing meetings), new tool environment, expanded data scope. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm the meeting itself is non-restricted (training, vendor briefing, public conference, fictional practice). Internal employer meetings require explicit approval.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before any row is used in a tracker. Required for any action that will leave Tom's hands (owner confirmation, escalation, official tracker).

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-02-meeting-notes-to-actions.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0040.
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-01-weekly-status-drafting.md`, `P-03-action-aging-summary.md`.
