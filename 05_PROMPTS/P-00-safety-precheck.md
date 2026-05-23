# P-00-safety-precheck - Universal pre-flight safety precheck

## Prompt identity

- **ID:** P-00
- **Paired workflow:** none — this is a utility prompt that runs before every paired prompt (P-01..P-12) and before any unpaired AI session inside ATLAS.
- **Backlog ID:** none — not tracked as a backlog row; behavior is required by every paired prompt's §12 and by the universal rules in `PROMPT_LIBRARY.md`.
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

A short, repeatable checklist Tom runs in his head (or pastes into the AI tool itself) before sending any ATLAS prompt. It enforces the Phase 3 pre-flight expectations in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI" and the classification step in `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md` "Classification flow." If the precheck fails on any line, the AI step does not run.

## 2. Paired workflow and PM/Ops role

Not paired with a single workflow. Every paired prompt's §12 cites this file. The AI role here is zero — `P-00` is a discipline gate Tom runs against himself before the AI is invited into the loop. Optionally, the precheck text can be pasted into the AI session as a stated context block so the AI knows the input has been classified.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): n/a — the precheck determines the category; it does not have its own.
- **Tool environment** (same file, "Tool environments"): n/a — the precheck determines the environment.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): n/a.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): n/a.

## 4. Safe input requirements

- A candidate AI prompt and the source material the prompt will operate on.
- The paired workflow card (W-NN), if any, so the data category and review intensity from §4 of that card are visible.

## 5. Prohibited input warning

In the default personal-preparation environment, the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per the migration section of the paired W-NN card and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Any input the classifier cannot place into Synthetic, Public, Tom-personal, or Employer-approved with confidence. Default to Prohibited.
- Any input that paraphrases restricted content (paraphrased restricted content is restricted content, per `DATA_SENSITIVITY_DECISION_MODEL.md` "Things that look safer than they are").

## 6. Placeholders used

The §7 text uses these placeholders. Replace them before running the precheck.

- `[CANDIDATE_INPUT]` — the source material to be sent to the AI tool.
- `[PAIRED_W_ID]` — the paired workflow card ID (e.g., `W-01`); use `none` for unpaired sessions.
- `[NAMED_REVIEWER]` — the human who will sign off on the AI output (Tom by default).
- `[CHOSEN_TOOL_ENVIRONMENT]` — `Personal AI tool`, `Employer-approved AI tool`, etc.

## 7. Copy-paste prompt text

`P-00` is not a prompt to send to the AI; it is a checklist Tom runs first. The text below is the checklist itself. Optionally, Tom can paste the completed checklist into the AI session as a "context" block; it does not need a response from the AI.

```text
ATLAS pre-flight safety precheck (P-00)

Source material to be sent: [CANDIDATE_INPUT]
Paired workflow card: [PAIRED_W_ID]
Named reviewer: [NAMED_REVIEWER]
Chosen tool environment: [CHOSEN_TOOL_ENVIRONMENT]

Run each line. If any line is "no" or "uncertain," stop. Do not run the AI step.

[ ] 1. Classify the input per DATA_SENSITIVITY_DECISION_MODEL.md "Classification flow."
       Category (one of Synthetic / Public / Tom-personal / Employer-approved / Prohibited):
       ____________

[ ] 2. The tool environment matches the input category per the routing rules in
       the same file. Personal AI tool only takes Synthetic, Public, or Tom-personal.
       Employer-approved data goes only to the specific employer-approved AI tool
       with approval in scope.

[ ] 3. The named human reviewer is identified above and is willing to sign off.

[ ] 4. The review intensity is chosen (Light / Standard / Strict), matching the
       paired W-NN card's §4 or, for unpaired sessions, the rule in
       HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md.

[ ] 5. The "good" and "bad" criteria for the output are written down, either in
       the paired W-NN §11 ("Quality checks") or in a one-line note next to this
       precheck.

[ ] 6. The recording mechanism for sign-off is known (sign-off line in the output;
       audit envelope in approved venue for employer-deployable runs).

[ ] 7. The input does not paraphrase restricted content; it does not contain real
       program names, real customer names, real contract values, real EVM data,
       real schedule IDs from any employer system; it does not include screenshots
       of internal systems or filenames that reveal restricted detail.

[ ] 8. The AI's role for this session is limited to: structure / compare /
       summarize / draft / flag inconsistencies. The AI will not decide, approve,
       escalate, or send.

If any line is unchecked or "uncertain": stop. Reclassify, reroute, or rework
the input before invoking AI.
```

## 8. Expected output

Not applicable. `P-00` produces no AI output. Its output is a "go" or "stop" decision Tom makes before invoking the paired prompt's §7 text.

## 9. Human review checklist

`P-00` is itself a review checklist. The reviewer (Tom) confirms each of the eight lines above is checked or accounted for before the AI step runs. If `P-00` is being run for an employer-deployable session, the accountable owner from the paired W-NN card also confirms lines 1, 2, 4, 6, and 7.

## 10. Failure modes and escalation triggers

Failure modes the precheck is designed to surface:

- "Quick" sessions where the user skips classification.
- Mixed inputs (a synthetic file with a real name in it; a Tom-personal note that paraphrases a restricted briefing).
- Implicit reviewer assumptions ("Tom will look at it later") that never get recorded.
- Mismatch between tool environment and data category (Tom-personal data in an employer-approved tool; employer-approved data in a personal AI tool).

Escalation triggers:

- Input cannot be classified with confidence — stop, reclassify, or treat as Prohibited.
- No willing reviewer — the AI step does not run.
- Tool environment cannot be matched to category — stop, change tool or change scope.
- Employer policy conflicts with the classification flow — employer policy wins (per `DATA_SENSITIVITY_DECISION_MODEL.md` "When this model conflicts with explicit employer guidance"); update `AI_GOVERNANCE_NOTES.md` and `DECISION_LOG.md` to reflect the new known information.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Tom runs the 8-line checklist before any P-NN prompt. Sign-off is the act of proceeding to the paired prompt.
- **Employer-deployable form (after approval):** The precheck is run by Tom plus the accountable owner from the paired W-NN card. Lines 1, 2, 4, 6, and 7 are recorded as part of the audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums."
- **Re-approval triggers:** A new tool environment, a new data category, or a new accountable owner. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

`P-00` is the safety precheck. It does not cite itself; instead it cites the upstream sources of the discipline: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md` "Classification flow" and `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."

## 13. Output critique pass (optional)

Not applicable. `P-00` produces no AI output to critique. `P-99-prompt-critique-and-output-qa.md` is the post-flight equivalent and runs after the paired prompt's output is in hand.

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md` (Classification flow, Routing rules, Things that look safer than they are), `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` (Pre-flight checklist), `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Library index: `05_PROMPTS/PROMPT_LIBRARY.md` "Universal prompt rules."
- Used by: every P-NN paired prompt's §12.
- Related utility prompt: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
