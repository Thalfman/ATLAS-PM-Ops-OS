# P-99-prompt-critique-and-output-qa - Prompt critique and output QA

## Prompt identity

- **ID:** P-99
- **Paired workflow:** (utility — applies to all P-NN prompts)
- **Backlog ID:** (none — utility prompt, not in the 11-row Phase 5 backlog)
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

A post-flight critique pass for any AI output produced by a paired P-NN prompt. P-99 turns the post-flight checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and the paired W-NN §11 "Quality checks" / "Red flags" into a self-administered or AI-administered review pass before the output is used. Required for Strict review intensity; recommended for Standard.

## 2. Paired workflow and PM/Ops role

P-99 is universal. It runs once per AI output, after the paired P-NN prompt produced its draft. The AI role is to critique, not to rewrite. P-99 returns a structured list of overclaims, hallucinations, missing fields, unsupported numbers, and tone problems. Tom (or the accountable owner) decides what to fix; AI does not silently edit the original.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Inherited from the paired P-NN prompt. P-99 does not change the data category.
- **Tool environment** (same file, "Tool environments"): Same environment as the paired P-NN. Do not move output to a different tool for critique unless the routing rule allows it.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): n/a (P-99 supports the chosen intensity; it does not set its own).
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Inherited from the paired P-NN.

## 4. Safe input requirements

- The AI-produced output from a paired P-NN prompt (the draft to critique).
- The paired prompt's ID and the paired workflow's ID (so the critique can apply the right W-NN §11 criteria).
- The original source list / input block that fed the paired P-NN (so the critique can check trace-to-source).

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Any draft that violated the paired P-NN's §5 prohibited-input warning. P-99 does not launder restricted content.
- Critique requests on output that was generated outside the paired P-NN pattern (e.g., free-form AI text not produced by an ATLAS prompt). The critique pass relies on the paired W-NN §7 output shape; without that anchor, the critique is unreliable.

## 6. Placeholders used

- `[PAIRED_PROMPT_ID]` — e.g., P-01, P-02, …, P-12.
- `[PAIRED_WORKFLOW_ID]` — e.g., W-01, W-02, …, W-12.
- `[AI_OUTPUT]` — the draft produced by the paired P-NN prompt.
- `[SOURCE_INPUT]` — the original input block the paired P-NN used.

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional critique an AI-produced draft before it is used.

CONTEXT
The draft below was produced by ATLAS prompt [PAIRED_PROMPT_ID], which pairs with workflow card [PAIRED_WORKFLOW_ID].
The critique must apply [PAIRED_WORKFLOW_ID]'s §11 "Quality checks" and "Red flags" verbatim — do not invent additional criteria.

INPUTS
- Paired prompt: [PAIRED_PROMPT_ID]
- Paired workflow: [PAIRED_WORKFLOW_ID]
- Original source input that fed the paired prompt:
[SOURCE_INPUT]
- AI draft to critique:
[AI_OUTPUT]

DO
- Identify every claim in the draft that does not trace to a line in the source input. Quote the claim and the missing source.
- Identify every number, name, date, owner, activity ID, or metric in the draft that the source does not contain. Quote it.
- Identify every overclaim (asserted cause, asserted recovery, asserted accounting determination, asserted commitment) and flag it as overclaim with one sentence of why.
- Identify every missing field (column with no value, section with no content) and flag whether the source actually supplied that field or not.
- Identify every tone issue: marketing language, blame language, hedging, smoothing. Quote the phrase.
- Note any "Red flags" from [PAIRED_WORKFLOW_ID] §11 that apply.

DO NOT
- Rewrite the draft.
- Fix the issues. The critique returns a list; the reviewer decides what to fix.
- Invent additional criteria beyond [PAIRED_WORKFLOW_ID] §11.
- Make policy judgments (those belong to the accountable owner).

OUTPUT FORMAT
Return a Markdown structure with these sections, in this order:

## Trace-to-source findings
[Bulleted list. One bullet per untraceable claim: "Claim: <quote>. Missing source: <what was expected>."]

## Fabricated detail findings
[Bulleted list. One bullet per item not in the source: "Item: <quote>. Source contains: <yes/no/which line>."]

## Overclaim findings
[Bulleted list. One bullet per overclaim: "Overclaim: <quote>. Why: <one sentence>."]

## Missing fields findings
[Bulleted list. One bullet per missing field: "Field: <name>. Source supplied: <yes/no>. Recommended action: flag as 'missing field' in the output, or supply from source."]

## Tone findings
[Bulleted list. One bullet per tone issue: "Phrase: <quote>. Category: <marketing/blame/hedging/smoothing>."]

## Workflow §11 red-flag matches
[Bulleted list. Each entry quotes the W-NN red flag and quotes the line in the draft that triggered it.]

## Critique summary
[One short paragraph stating whether the draft is ready for the reviewer's sign-off, needs a focused fix pass, or should be discarded and the paired P-NN re-run.]

End of critique.
```

## 8. Expected output

A structured Markdown critique with six labeled sections (Trace-to-source findings; Fabricated detail findings; Overclaim findings; Missing fields findings; Tone findings; Workflow §11 red-flag matches) plus a one-paragraph Critique summary. Length scales with the number of findings; expect 150-600 words for a typical paired P-NN output.

## 9. Human review checklist

The reviewer reads the critique and decides:

- Which findings to fix in the draft (Tom edits or re-prompts the paired P-NN; AI does not edit silently).
- Which findings are false positives (the critique misread the source; document briefly and move on).
- Whether the draft is ready for sign-off, needs a focused fix pass, or should be discarded and re-prompted.
- Whether any finding escalates per the paired W-NN §13 "Escalation triggers."

The reviewer follows the paired W-NN's per-domain review pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` to validate the critique's findings against the source.

## 10. Failure modes and escalation triggers

Failure modes:

- Critique flags items that are in the source (false positive). The reviewer must check before discarding draft content.
- Critique misses overclaims that the W-NN §11 "Red flags" name. Re-prompt with the explicit red-flag list pasted in.
- Critique rewrites the draft instead of flagging issues. Re-prompt with the "DO NOT rewrite the draft" line emphasized.
- Critique becomes a second draft. Reviewer treats P-99 output as a checklist, not a rewrite.

Escalation triggers:

- Critique surfaces a finding that crosses safety, compliance, contract, or customer territory — go to the accountable owner per the paired W-NN §13 before any further iteration.
- Critique finds the source itself is wrong or incomplete — go to the source owner; do not iterate the AI draft.
- Critique reveals Prohibited content in the draft — stop, do not iterate; reclassify and remove the AI step.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** P-99 runs in a Personal AI tool against output produced by a paired P-NN with synthetic or Tom-personal input. Findings inform Tom's edits; nothing else changes.
- **Employer-deployable form (after approval):** P-99 runs in the Employer-approved AI tool against output produced by an employer-approved-data run of the paired P-NN. Critique findings are part of the Strict-review audit envelope; the accountable owner signs off on the disposition of each finding before the output is used.
- **Re-approval triggers:** New data category in the paired P-NN; new tool environment; new accountable owner; broadening the critique scope (e.g., from PM/Ops critique to policy judgment). Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending P-99. The input is the AI output from the paired P-NN; classify the output as inheriting the paired P-NN's data category. If the paired P-NN failed P-00, P-99 does not run.

Prompt-specific precheck additions:

- Confirm the draft is from an ATLAS paired P-NN prompt, not free-form AI text.
- Confirm the original source input is available for trace-to-source checks.

## 13. Output critique pass (optional)

P-99 is itself the critique pass. Do not chain P-99 into another P-99 pass. If the critique itself looks unreliable, re-prompt the paired P-NN with cleaner inputs and re-run P-99 once.

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: none (utility).
- Backlog row: none (utility prompt; not in the 11-row Phase 5 backlog).
- Cited by: every paired P-NN card's §13.
- Related prompts: `P-00-safety-precheck.md` (pre-flight counterpart).
