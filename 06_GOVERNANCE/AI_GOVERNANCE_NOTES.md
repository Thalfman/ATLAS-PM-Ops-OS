# AI_GOVERNANCE_NOTES.md

## Purpose

These notes define the conservative AI posture for ATLAS PM/Ops OS. They are written for a federal/defense-adjacent environment where clearance, export-control, proprietary, customer, contract, financial, technical, and internal schedule data may be highly sensitive, and where employer AI policy may be unknown or evolving at the time a candidate workflow is considered.

The notes are personal-preparation material. They do not state Motorola Solutions internal policy, they do not give legal advice, and they do not create exceptions to any employer rule. Anything in this file is overridden by any explicit employer instruction once that instruction is known.

## How to use these notes

Use this file as the anchor reference for AI-enabled PM/Ops work in ATLAS. The companion files extend it:

- `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md` - candidate-selection, data-path classification, approved-tool selection, human-review, pilot, and documentation steps.
- `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md` - the per-input classification model that routes data to a tool environment.
- `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` - the reusable human-review-point pattern that workflows and prompts inherit.
- `06_GOVERNANCE/EMPLOYER_TOOL_APPROVAL_QUESTION_SET.md` - questions to ask managers, IT, security, and compliance once it is appropriate to ask.
- `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md` - how to talk about AI integration responsibly with management, IT, security, compliance, or program leadership.
- `06_GOVERNANCE/PROMPT_AND_OUTPUT_RETENTION_NOTE.md` - the conservative retention posture for prompts and outputs until employer policy is known.

Read this file first. Use the sibling files for the operational detail.

## Core governance principle

AI may support PM/Ops judgment by organizing information, drafting language, flagging inconsistencies, suggesting questions, and improving repeatability. AI must not replace accountable human judgment, make official decisions, bypass approved systems, or process sensitive data in unapproved tools.

Tool capability does not equal tool authorization. A tool being able to ingest, summarize, transform, or generate something is not evidence that the tool is approved for that data in that environment.

## Default operating posture

- Human-in-the-loop on every output that touches PM/Ops work.
- Approved-tool-first for any data that is not synthetic, public, generic, or fictional.
- Audit-friendly: source traceability, separation of facts/assumptions/AI suggestions, clear ownership.
- Gemini-first but platform-agnostic: design so a workflow can move to whichever tool is approved.
- No shadow IT. No autonomous decisions. No sensitive data in personal tools.
- Clear separation between personal preparation artifacts and employer-deployable artifacts.
- AI supports PM/Ops judgment; AI does not replace accountable human decision-making.

## Personal preparation artifacts vs employer-deployable artifacts

ATLAS distinguishes two artifact lifecycles. Both are in scope; treating them the same is unsafe.

- **Personal preparation artifact.** Lives in this repo. Built with synthetic, public, generic, fictional, or Tom-authored non-proprietary material. Used to practice, demonstrate value with fictional examples, or build muscle memory before onboarding. Never carries employer data. Always portable.
- **Employer-deployable artifact.** A version of a personal artifact that has been approved for use with employer data inside an approved tool, with the appropriate human-review and audit trail. Lives where the employer says it should live, not in this repo. Requires written or otherwise documented approval before it processes any employer data.

A personal preparation artifact does not become an employer-deployable artifact by being copy-pasted into an employer tool. The conversion requires explicit tool approval, data-path classification, a defined human-review point, and acceptance from the accountable owner.

## Tool posture

### Preferred starting posture

- Use employer-approved tools only for employer data.
- Assume Gemini Enterprise may be the first approved AI tool.
- Keep workflows platform-agnostic and portable.
- Use personal tools only for synthetic, public, generic, or fictional material.

### Tools that may require explicit approval before workplace use

This list is illustrative and conservative. Treat any tool not on an approved list as unapproved by default.

- Personal ChatGPT/OpenAI
- Claude (consumer or API)
- Codex or other coding agents
- External APIs (Anthropic, OpenAI, Google AI Studio, etc.)
- CLI tools connected to employer data
- MCP servers
- Browser extensions that read page contents
- Unapproved automation tools (Zapier, Make, custom scripts that move employer data)
- Any tool that stores, trains on, exports, or transmits employer data outside approved boundaries

## Prohibited inputs for personal or unapproved AI tools

Do not input any of the following into any personal or unapproved AI tool, in any form, including paraphrased, partial, summarized, screenshotted, or filename-only:

- Classified information
- CUI (Controlled Unclassified Information)
- ITAR or export-controlled data
- Proprietary employer data
- Customer data
- Contract data, including terms, pricing, deliverables
- Internal schedules (Microsoft Project files, plans, milestones tied to real programs)
- Internal financials (labor, EAC, ETC, variances tied to real programs)
- Internal technical documents
- Nonpublic program names
- Real meeting notes (your own or others')
- Real project accounting extracts
- Real Microsoft Project files
- Real internal reports
- Screenshots of internal systems
- Any nonpublic information not explicitly approved for that specific tool

If you are unsure whether a piece of information falls into the above, treat it as prohibited.

## Safe inputs for personal preparation

Allowed for personal preparation work in ATLAS:

- Synthetic scenarios authored by Tom or recognizable as fictional
- Fictional projects with invented names, dates, and figures
- Generic PM/Ops examples (any PMP/PMI-style language)
- Public information (published news, public standards, public training material)
- Tom-authored templates that contain no employer data
- Training examples that do not resemble real internal data
- Tom's own personal notes about his preparation (not employer meeting notes)

## Human-in-the-loop controls

Every AI-enabled workflow in ATLAS must include all of the following. Workflows missing any of these are not ready for use against real data.

1. Human review before use. The accountable human reads the AI output and approves it before anything happens with it.
2. Source traceability. Anyone reviewing the output can see what input was used.
3. Clear separation between facts, assumptions, and suggested language. The output marks which is which.
4. A way to mark uncertainty. The output does not pretend to know things it does not know.
5. No autonomous sending, filing, approval, or escalation by the tool.
6. A named accountable human owner for the output.
7. An audit trail when used in official work.

See `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` for how these controls are implemented at the workflow level.

## Data classification checklist before using AI

Before putting anything into an AI tool, run through these questions. If any answer is uncertain, do not use the AI tool with that data.

1. Is the tool approved for this data type, in writing or by documented practice?
2. Is the data public, synthetic, generic, or explicitly approved for this tool?
3. Could the data reveal customer, contract, program, schedule, financial, technical, or personnel information?
4. Could the data be CUI, ITAR/export-controlled, classified, or proprietary?
5. Could a screenshot, filename, project code, or metadata reveal something sensitive?
6. Is there a lower-risk way to get the same PM/Ops outcome (a template, a manual check, a non-AI tool)?
7. Has a human reviewer approved the workflow that uses this AI step?

`DATA_SENSITIVITY_DECISION_MODEL.md` operationalizes this checklist as a routing model.

## AI workflow maturity levels

| Level | Description | Suitable during pre-start? | Suitable at work? |
|---:|---|---|---|
| 0 | Personal synthetic practice | Yes | Not for employer data. |
| 1 | Generic templates and prompts | Yes | Yes, if no sensitive data is included. |
| 2 | Approved-tool drafting with approved data | No, unless data is synthetic | Yes, with approval and human review. |
| 3 | Approved workspace workflow with audit trail | No | Yes, if approved by employer governance. |
| 4 | Integrated automation across systems | No | Only after formal approval, security review, and process validation. |

Most ATLAS pre-start artifacts target Level 0 or Level 1. Levels 2 through 4 are only reachable inside an employer-approved environment.

## Access control and need-to-know

Even when a tool is approved for a data category, that does not mean a given person is authorized to see specific instances. Access control and need-to-know principles continue to apply:

- Do not put data into an AI tool that the recipient (or the tool's storage backend) is not cleared to see.
- Do not use AI summarization to widen access to information that would otherwise be restricted.
- Do not use AI to merge or join data sets that policy keeps separated.
- If unsure whether merging two data sources is appropriate, do not use AI for the join; raise the question through the appropriate channel.

## Version control, document ownership, and audit trail

For employer-deployable artifacts:

- Store outputs where the employer expects them to live (the approved workspace, repository, or document system).
- Name an accountable owner for each artifact.
- Preserve a record of what input was used to produce the output, what AI tool was used, and who approved the result.
- Treat AI output as a draft until a human approves it. Approval should be documented.
- Do not silently overwrite prior versions; keep enough history that a reviewer can reconstruct what changed and why.

For personal preparation artifacts in ATLAS:

- Use the repo's commit history as the audit trail.
- Update `09_HANDOFFS/SESSION_HANDOFF.md` and `10_DECISION_LOG/DECISION_LOG.md` per the session-end protocol.

## Risk review before workflow migration

Before migrating a personal preparation workflow into an employer environment:

1. Confirm the candidate tool is approved for the intended data category.
2. Re-run the data classification checklist against representative real inputs (without putting real inputs into a personal tool).
3. Identify the named human reviewer and confirm they accept the role.
4. Define what "good" and "bad" output look like, and how a reviewer would tell.
5. Pilot with synthetic or sanitized examples first.
6. Document benefits, limitations, residual risks, and stop conditions.
7. Get explicit approval from the accountable owner before any real data flows through the workflow.

This sequence is detailed further in `AI_TOOL_APPROVAL_STRATEGY.md`.

## Clearance-limited onboarding considerations

During clearance-limited onboarding, Tom may be physically or logically separated from cleared work areas, real meeting notes, real schedules, and real financial data. The governance implications:

- It is safer than usual, in the sense that the data Tom can see is more constrained.
- It is also a sensitive period for trust-building. Avoid actions that could be read as workarounds: do not paraphrase restricted briefings into personal tools, do not retain materials from restricted areas in personal storage, do not use AI to fill in gaps in restricted information.
- Build value with synthetic demonstrations, generic templates, listening exercises, and process-gap notes, not with employer data.
- Use the `EMPLOYER_TOOL_APPROVAL_QUESTION_SET.md` and `AI_CONVERSATION_GUIDE.md` to learn what is permitted before proposing any AI workflow against employer data.

## Red flags

Stop and seek guidance if a workflow involves:

- Export-controlled or classified technical content
- Customer-specific information
- Contract terms or deliverables
- Program names not public
- Internal financial or labor data
- Sensitive schedule data
- Unapproved tools
- Automated communications or escalations
- AI making recommendations that could be interpreted as official decisions
- Merging data sets that policy keeps separated
- Anything the data classification checklist flagged as uncertain

## Governance note for ATLAS artifacts

Every ATLAS artifact should:

- State its safe-input assumption.
- Be easy to sanitize.
- Name a human review point if its output ever touches real data.
- Avoid baking in employer-specific facts or policy claims.

Employer-specific versions of any artifact should be created only after tool and data approvals are confirmed, and they should live in the approved environment, not in this repo.
