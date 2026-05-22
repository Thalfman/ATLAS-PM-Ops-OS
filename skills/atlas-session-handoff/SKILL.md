# atlas-session-handoff Skill

## Purpose

Use this skill to end every significant ATLAS work session with a durable handoff. The handoff prevents context loss and makes the next session easy to continue without restating the project.

## When to use

Use this skill:

- At the end of any meaningful ATLAS work session
- After creating or changing files
- After making design, governance, or roadmap decisions
- Before stopping work for the day
- When preparing a next best prompt for continuation

## Required source files

1. `09_HANDOFFS/SESSION_HANDOFF_TEMPLATE.md`
2. `09_HANDOFFS/SESSION_HANDOFF.md`
3. `00_MASTER_CONTEXT/MASTER_CONTEXT.md`
4. `10_DECISION_LOG/DECISION_LOG.md` if decisions were made

## Handoff rules

- Always identify the current phase.
- List files changed.
- Summarize completed work in plain language.
- Record decisions and rationale.
- Re-state safety-relevant cautions if the next session may touch AI, employer workflows, data, or migration.
- Identify open questions and next recommended work.
- Include one copy-paste-ready next best prompt.
- Do not include sensitive employer data.

## Required handoff sections

Use these sections:

```text
## Session date
## Current phase
## Current status
## Files changed
## Decisions made
## Safety review
## Open items
## Recommended next phase or artifact
## Next best prompt
```

## Safety review language

Every handoff should confirm whether:

- No real employer data was used.
- No classified, CUI, ITAR/export-controlled, proprietary, customer, contract, internal schedule, internal finance, or internal technical data was used.
- All examples were synthetic, public, generic, fictional, or approved.
- Human-in-the-loop posture remains intact.
- No unapproved tooling assumptions were introduced.

## Next best prompt guidance

The next best prompt should:

- Tell the assistant to read `MASTER_CONTEXT.md` and `SESSION_HANDOFF.md` first.
- Name the phase or artifact to continue.
- Restate the safety boundary briefly.
- Preserve the Markdown-first, Gemini-first, platform-agnostic, PM/Ops outcome-focused posture.
- Ask for the handoff file to be updated at the end.
