# SESSION_HANDOFF_TEMPLATE.md

Use this template to overwrite `09_HANDOFFS/SESSION_HANDOFF.md` at the end of every ATLAS work session that produced changes. Keep it short enough to actually use.

## Session date

[YYYY-MM-DD]

## Current phase

[Phase number and name, for example "Phase 1 - Master Context and Continuity System"]

## Session objective

[One or two sentences on what this session intended to accomplish.]

## Source-of-truth review

Confirm:

- [ ] Read `00_MASTER_CONTEXT/MASTER_CONTEXT.md` at session start.
- [ ] Read the previous `09_HANDOFFS/SESSION_HANDOFF.md` at session start.
- [ ] Working directory confirmed as `C:\Users\thalf\OneDrive\Documents\ATLAS-PM-Ops-OS`.
- [ ] Phase prompt at `05_PROMPTS/PHASE_PROMPTS/PHASE_##_*.md` consulted if applicable.

## Files changed

| Path | Type of change | Summary |
|---|---|---|
| `[path]` | [added / updated / removed] | [one-line summary] |

## Completed work

- [Completed item]
- [Completed item]

## Decisions made

| Decision | Rationale | File or area impacted |
|---|---|---|
| [Decision] | [Why] | [Path or area] |

If any decision is durable, also append it to `10_DECISION_LOG/DECISION_LOG.md`.

## Safety review

Confirm:

- [ ] No real employer data used.
- [ ] No classified data used.
- [ ] No CUI used.
- [ ] No ITAR or export-controlled data used.
- [ ] No proprietary, customer, contract, internal schedule, internal finance, or internal technical data used.
- [ ] No real program names, real meeting notes, real Microsoft Project files, or real project accounting exports used.
- [ ] All examples are synthetic, public, generic, fictional, or user-created.
- [ ] Human-in-the-loop posture preserved.
- [ ] Gemini-first and platform-agnostic posture preserved.
- [ ] No app, package, API, database, deployment, or code scaffolding added unless explicitly requested.

## Definition-of-done check

Confirm:

- [ ] Every artifact created or updated is Markdown-first and portable.
- [ ] Every artifact has a clear purpose and an obvious human review step where relevant.
- [ ] No artifact assumes access or data Tom may not have during clearance-limited onboarding.
- [ ] This handoff file is up to date and contains the next best prompt.

## Open items

- [Open question or pending task]
- [Open question or pending task]

## Risks and cautions

- [Risk or caution that the next session should respect]
- [Risk or caution that the next session should respect]

## AI tooling notes

[Briefly note any assumptions about AI tools, approval status, or platform migration that the next session should be aware of. Keep this generic; do not assert employer policy.]

## Recommended next phase or artifact

[For example "Phase 2: Roadmap and Artifact Backlog" or "Refine governance checklist".]

## Next best prompt

Use this exact block for the next ATLAS session. It should tell the assistant to read source-of-truth files first, name the phase or artifact, restate the safety boundary in one line, preserve the Markdown-first and Gemini-first posture, and end by updating the handoff file.

```text
Continue ATLAS PM/Ops OS.

Local repo path:
C:\Users\thalf\OneDrive\Documents\ATLAS-PM-Ops-OS

Source-of-truth files to read first:
1. 00_MASTER_CONTEXT/MASTER_CONTEXT.md
2. 09_HANDOFFS/SESSION_HANDOFF.md
3. 05_PROMPTS/PHASE_PROMPTS/PHASE_##_*.md  (use the file named below)

Phase to run:
[Phase number and name]

Phase prompt file:
05_PROMPTS/PHASE_PROMPTS/[PHASE_##_*.md]

Safety boundary (one line):
Use only synthetic, public, generic, fictional, or user-created non-proprietary material. Do not use classified, CUI, ITAR/export-controlled, proprietary, customer, contract, internal schedule, internal finance, internal technical, real meeting note, real Microsoft Project, or real accounting data.

Posture:
Markdown-first, Gemini-first, platform-agnostic, human-in-the-loop, approved-tool-first. Do not add apps, package dependencies, APIs, databases, deployment files, or code scaffolding. Update 09_HANDOFFS/SESSION_HANDOFF.md at the end.
```
