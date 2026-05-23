# PROMPT_CARD_TEMPLATE.md

Reusable template for every ATLAS prompt card. Copy this file to `05_PROMPTS/P-NN-<slug>.md`, replace bracketed placeholders, and append a row to the index in `PROMPT_LIBRARY.md`. Do not redefine governance language; cite the Phase 3 bundle by filename and section. Do not redefine workflow language; cite the paired `04_WORKFLOWS/W-NN-<slug>.md` card.

The 14 sections below cover the 7 required fields from the Phase 5 prompt (use case, safe input requirements, prohibited input warning, copy-paste prompt text, expected output, human review checklist, notes for approved-tool migration) plus the governance envelope, the paired-workflow citation, a placeholders list, failure modes, a safety precheck citation, identity, and cross-references.

---

# P-NN-<slug> - <Prompt Name>

## Prompt identity

- **ID:** P-NN
- **Paired workflow:** W-NN (`04_WORKFLOWS/W-NN-<slug>.md`)
- **Backlog ID:** A-NNNN
- **Status:** Drafting | Ready for personal use | Deferred
- **Last updated:** YYYY-MM-DD

## 1. Use case

[One short paragraph. Name the PM/Ops failure mode the prompt addresses and the deliverable it produces. Pull this from the paired W-NN §2 and §3.]

## 2. Paired workflow and PM/Ops role

[One short paragraph. Name the paired W-NN by ID and slug; state which step(s) of the workflow's §10 process this prompt executes; restate the AI role (structure, compare, summarize, draft, flag — never decide, approve, escalate, or send).]

## 3. Governance envelope

Cite the Phase 3 bundle by filename and section. Do not re-define these.

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): [Synthetic | Public | Tom-personal | Employer-approved | Prohibited]
- **Tool environment** (same file, "Tool environments"): [ATLAS-local Markdown | Personal AI tool | Employer-approved AI tool | No AI tool]
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): [Light | Standard | Strict]
- **Per-domain review pattern** (same file, "Per-domain review patterns"): [Status and reporting | Schedule | Finance, EVM, and project accounting | Meeting notes to action items | Risk and issue triage | SOP and lessons-learned]

If two categories or environments seem to apply, take the more restrictive one (per `DATA_SENSITIVITY_DECISION_MODEL.md`).

## 4. Safe input requirements

- [Bullet list. Mirror the paired W-NN §5. Only synthetic, public, or Tom-personal inputs unless §3 routes to an employer-approved tool.]

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- [Bullet list. Mirror the paired W-NN §6. At minimum: classified, CUI, ITAR or export-controlled, proprietary, customer, contract, internal schedule, internal finance, internal technical, real meeting notes, real Microsoft Project files, real accounting exports — unless §3 explicitly routes to an employer-approved tool for an approved data scope.]

## 6. Placeholders used

The prompt text in §7 uses the following fictional placeholders. Replace them with synthetic or Tom-personal content before sending the prompt. Do not replace any placeholder with employer data in a personal AI tool.

- `[SYNTHETIC_PROJECT_NAME]` — name of the fictional project.
- `[PLACEHOLDER_OWNER]` — fictional or Tom-personal owner name.
- `[APPROVED_INPUT]` — the safe input block (paste the source material here).
- [Add prompt-specific placeholders, e.g., `[FICTIONAL_VARIANCE]`, `[SYNTHETIC_PERIOD]`, `[FICTIONAL_ACTIVITY_ID]`.]

## 7. Copy-paste prompt text

```text
[Gemini-first phrasing. Platform-agnostic. Includes:
 - Role statement ("You are an assistant helping a PMP-certified PM/Ops professional…").
 - Inputs section with placeholders.
 - Output format spec referencing the paired W-NN §7.
 - Forbid-list (do not invent facts, do not name causes, do not decide, do not send).
 - Output discipline (return the table or narrative only; flag missing fields, do not fill them by inference).
]
```

## 8. Expected output

[Concrete shape: section headings, table columns, narrative length. Match what Tom would actually paste into a report or doc. Mirror the paired W-NN §7.]

## 9. Human review checklist

The reviewer (Tom by default; named accountable owner for employer-deployable runs) follows the per-domain pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist in the same file before using the output:

- [3-5 bullets. Lift the matching per-domain pattern's bullets verbatim from `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`. Add 1-2 prompt-specific checks where useful.]

## 10. Failure modes and escalation triggers

Failure modes the prompt is designed to surface, not paper over:

- [3-5 bullets, mirroring paired W-NN §13. Things AI will produce that look right but are not.]

Escalation triggers (stop iterating the AI draft, go to a human):

- [3-5 bullets. When to put the prompt down and pick up the phone.]

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** [How the prompt runs in a Personal AI tool with synthetic or Tom-personal inputs. Mirror paired W-NN §14 "Personal-preparation form."]
- **Employer-deployable form (after approval):** [What changes when the prompt runs against Employer-approved data in an Employer-approved AI tool: review intensity rises to Strict, full audit envelope captured per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums," accountable owner named. Mirror paired W-NN §14 "Employer-deployable form."]
- **Re-approval triggers:** [Any change that requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`. Mirror paired W-NN §14 "Re-approval triggers."]

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7. P-00 covers the universal classification step, the tool-environment check, the reviewer-named check, and the recording-mechanism check.

Prompt-specific precheck additions:

- [0-3 bullets unique to this prompt — e.g., "If the input mentions a real customer name, stop. Reclassify." Most prompts will add zero or one bullet here.]

## 13. Output critique pass (optional)

After the AI returns the §8 output, optionally run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the output for a second-pass quality review. The critique pass is required for any output that will leave Tom's hands (employer-deployable, Strict review intensity).

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-NN-<slug>.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-NNNN.
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: [P-NN, P-NN].
