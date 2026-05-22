# AI_GOVERNANCE_NOTES.md

## Purpose

These notes define the safe AI posture for ATLAS PM/Ops OS. They are designed for a federal/defense-adjacent environment where clearance, export-control, proprietary, customer, contract, financial, technical, and internal schedule data may be highly sensitive.

## Core governance principle

AI may support PM/Ops judgment by organizing information, drafting language, flagging inconsistencies, suggesting questions, and improving repeatability. AI must not replace accountable human judgment, make official decisions, bypass approved systems, or process sensitive data in unapproved tools.

## Tool posture

### Preferred starting posture

- Use employer-approved tools only for employer data.
- Assume Gemini Enterprise may be the first approved AI tool.
- Keep workflows platform-agnostic and portable.
- Use personal tools only for synthetic, public, generic, or fictional material.

### Tools that may require explicit approval before workplace use

- Personal ChatGPT/OpenAI
- Claude
- Codex or coding agents
- External APIs
- CLI tools connected to employer data
- MCP servers
- Browser extensions
- Unapproved automation tools
- Any tool that stores, trains on, exports, or transmits employer data outside approved boundaries

## Prohibited inputs for personal or unapproved AI tools

Do not input:

- Classified information
- CUI
- ITAR/export-controlled data
- Proprietary employer data
- Customer data
- Contract data
- Internal schedules
- Internal financials
- Internal technical documents
- Nonpublic program names
- Real meeting notes
- Real project accounting extracts
- Real Microsoft Project files
- Real internal reports
- Screenshots of internal systems
- Any nonpublic information not approved for that specific tool

## Safe pre-start inputs

Allowed for personal preparation:

- Synthetic scenarios
- Fictional projects
- Generic PM/Ops examples
- Public information
- Tom-authored templates without employer data
- Training examples that do not resemble real internal data

## Human-in-the-loop controls

Every AI-enabled workflow should include:

1. Human review before use.
2. Source traceability.
3. Clear separation between facts, assumptions, and suggested language.
4. A way to mark uncertainty.
5. No autonomous sending, filing, approval, or escalation.
6. A named accountable human owner.
7. An audit trail when used in official work.

## Data classification checklist before using AI

Before putting anything into an AI tool, ask:

1. Is the tool approved for this data type?
2. Is the data public, synthetic, generic, or explicitly approved?
3. Could the data reveal customer, contract, program, schedule, financial, technical, or personnel information?
4. Could the data be CUI, ITAR/export-controlled, classified, or proprietary?
5. Could a screenshot, filename, project code, or metadata reveal something sensitive?
6. Is there a lower-risk way to get the same PM/Ops outcome?
7. Has a human reviewer approved the workflow?

If any answer is uncertain, do not use the AI tool with that data.

## AI workflow maturity levels

| Level | Description | Suitable during pre-start? | Suitable at work? |
|---:|---|---|---|
| 0 | Personal synthetic practice | Yes | Not for employer data. |
| 1 | Generic templates and prompts | Yes | Yes, if no sensitive data is included. |
| 2 | Approved-tool drafting with approved data | No, unless data is synthetic | Yes, with approval and human review. |
| 3 | Approved workspace workflow with audit trail | No | Yes, if approved by employer governance. |
| 4 | Integrated automation across systems | No | Only after formal approval, security review, and process validation. |

## Questions for employer AI/tool approval discussions

Use these questions after onboarding, in appropriate channels:

1. Which AI tools are approved for employee use today?
2. Which data types are approved for each tool?
3. Are there written rules for CUI, ITAR/export-controlled, proprietary, customer, contract, technical, financial, and schedule data?
4. Is Gemini Enterprise approved for internal document summarization, drafting, spreadsheet analysis, or workflow support?
5. Are there approved prompt logging, retention, or audit requirements?
6. Are employees allowed to use AI for meeting note summarization? Under what conditions?
7. Can AI be used with Microsoft Project, Excel, or Google Sheets outputs? If yes, which fields/data classes are allowed?
8. Who approves new AI-enabled workflows?
9. What is the process for piloting a low-risk AI workflow?
10. What documentation is required before migrating a local template into an employer workflow?

## Recommended pilot strategy

Start with low-risk, high-utility workflow pilots:

1. Generic reporting structure improvement with no sensitive data.
2. SOP draft formatting from approved, non-sensitive process notes.
3. Action item table formatting from approved meeting outputs.
4. Risk wording cleanup using approved risk register fields only if allowed.
5. Synthetic demo pack for discussion before any real data is used.

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

## Governance note for ATLAS artifacts

Every artifact should include a safe-input assumption and should be easy to sanitize. Employer-specific versions should be created only after tool and data approvals are confirmed.
