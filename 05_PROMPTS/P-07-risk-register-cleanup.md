# P-07-risk-register-cleanup - Risk register cleanup

## Prompt identity

- **ID:** P-07
- **Paired workflow:** W-07 (`04_WORKFLOWS/W-07-risk-register-cleanup.md`)
- **Backlog ID:** A-0042
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Convert a vague, inconsistent risk register into a cleaned register with condition-consequence statements, explicit triggers, named owners, current probability and impact, response status, and a separate hygiene-notes list (duplicates, retirement candidates, missing fields, themes). The prompt addresses W-07 §2: registers as "a list of words rather than a usable tool." The deliverable is the two-part output described in W-07 §7.

## 2. Paired workflow and PM/Ops role

Paired with `W-07-risk-register-cleanup.md`. Executes steps 4-6 of the W-07 §10 process: rewrite vague statements into condition-consequence form, flag missing fields, propose duplicates and retirement candidates. AI role: rewrite, flag, propose. AI must not invent owners, assign probability/impact without basis, or silently retire risks.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real risk register content is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for risk content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real register.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Risk and issue triage outputs.

## 4. Safe input requirements

Mirror W-07 §5:

- Synthetic risk register entries with fictional risks, owners, and mitigations.
- Generic risk examples from public PMI material.
- Tom's own notes from public risk-management training.

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-07 §6:

- Real risk registers from any employer system without explicit approval.
- Real owner names, contract risks, customer risks, or financial exposure detail.
- Risks that reveal restricted technical or program content.

## 6. Placeholders used

- `[SYNTHETIC_PROJECT_NAME]` — fictional project name.
- `[APPROVED_INPUT]` — the current register snapshot (Markdown table with whatever columns it has today).
- `[PLACEHOLDER_OWNER]` — fictional risk-owner names that appear in the register.

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional clean up a risk register.

ROLE
- Rewrite each entry into condition-consequence form ("If X happens, then Y occurs because Z").
- Flag missing fields by label ("missing field"); do not fill missing fields by inference.
- Propose duplicates and retirement candidates with stated reasons.
- Do not invent owners, triggers, or response statuses.
- Do not assign probability or impact unless the input provides judgment behind it.
- Do not silently retire risks; retirement is always a proposal, never a deletion.

INPUTS
- Project: [SYNTHETIC_PROJECT_NAME]
- Current register snapshot:
[APPROVED_INPUT]
- Known risk owners: [PLACEHOLDER_OWNER]

OUTPUT FORMAT

PART 1 — Cleaned register table

| # | Condition | Consequence | Trigger | Owner | Probability | Impact | Response (avoid / mitigate / transfer / accept) | Response status | Notes |
|---|---|---|---|---|---|---|---|---|---|

Each row mirrors an entry in the input register, in the same order. If the input did not contain a field, that cell is "missing field." Probability and Impact carry over only if the input shows judgment behind them (a rating, a rationale); otherwise mark as "missing field — owner input needed."

PART 2 — Hygiene notes

- **Duplicates merged (proposed)** — bullets listing original entry numbers and the reason for proposing a merge. Do not merge silently; flag for owner sign-off.
- **Candidates for retirement (proposed)** — bullets naming entries whose trigger has passed or whose condition is no longer present, with reason.
- **Entries with missing fields** — bullets listing each entry number and which fields are missing.
- **Themes** — bullets where multiple entries appear to be the same underlying risk under different framings; cite entry numbers.

DISCIPLINE
- Do not change any Owner field unless the input shows the owner moved; if you propose an owner change, list it under hygiene notes, not in Part 1.
- Do not change Probability or Impact ratings; if they look wrong, flag in hygiene notes ("entry N rating may not match the stated condition").
- If the input register contains restricted content (real customer name, real contract reference, real internal program code), stop and return only "PRECHECK FAIL — restricted content detected in input."

Return Part 1, Part 2, and nothing else.
```

## 8. Expected output

Part 1: a ten-column cleaned register table, one row per input entry, preserving order. Part 2: four labeled hygiene-notes lists (duplicates merged, candidates for retirement, entries with missing fields, themes). Mirrors W-07 §7.

## 9. Human review checklist

The reviewer (Tom for synthetic practice; risk owners for any real register) follows the "Risk and issue triage outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist before using the output:

- Confirm each entry has condition, consequence, trigger, owner (or "missing field" — never an AI guess).
- Confirm probability and impact match the judgment, not an AI guess.
- Confirm responses are actionable and owned.
- Confirm duplicates and retirement candidates are clearly separated, not silently merged.
- Confirm sensitive content (program names, customer detail) does not appear in the cleaned register.
- For real registers: risk-owner sign-off per entry before the cleaned register replaces the original.

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-07 §13):

- AI invents owners, triggers, or response statuses.
- AI silently retires a risk that still applies.
- AI merges entries that are actually distinct risks with shared symptoms.
- Probability and impact get inflated or deflated without judgment behind them.
- Reviewer accepts the cleaned register without risk-owner sign-off.

Escalation triggers:

- A risk crosses into safety, compliance, or contract obligation — go to program lead and accountable owner directly.
- A risk is owned by someone who has not yet seen the cleaned entry — go to that owner before any official update.
- A risk turns out to involve Prohibited data (real customer behavior, real contract terms) — stop, do not use AI; reclassify.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Synthetic register, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real register, Employer-approved AI tool against approved scope, Strict review, risk-owner sign-off per entry, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums," stored in approved venue.
- **Re-approval triggers:** Broadening scope to risk-response modeling or quantitative analysis; including contract or customer-facing risks; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm the register entries do not reference real customer behavior, real contract terms, or real program codes for personal-preparation runs.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before any cleaned entry replaces an original. Required for Strict review intensity.

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-07-risk-register-cleanup.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0042.
- Related demo: A-0052 Synthetic Risk Register Cleanup Demo (Phase 7).
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-08-issue-and-discrepancy-triage.md`.
