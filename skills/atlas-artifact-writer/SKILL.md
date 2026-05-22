# atlas-artifact-writer Skill

## Purpose

Use this skill to draft or refine ATLAS artifacts such as templates, prompts, workflow cards, governance notes, synthetic demos, checklists, SOP drafts, executive narratives, and readiness kits.

## When to use

Use this skill when creating or improving:

- PM/Ops templates
- Workflow library entries
- Prompt library entries
- Governance checklists
- Synthetic demo packs
- Schedule or EVM support artifacts
- Lessons learned or SOP artifacts
- Executive summaries or narrative templates

## Required context

Before writing, consult:

1. `00_MASTER_CONTEXT/MASTER_CONTEXT.md`
2. `09_HANDOFFS/SESSION_HANDOFF.md`
3. Relevant roadmap/backlog/workflow/governance files

## Artifact writing rules

- Use synthetic, public, generic, fictional, or approved material only.
- Do not include employer-sensitive data or invented employer specifics.
- Write for PM/Ops execution, not abstract AI transformation.
- Use clear headings and reusable structure.
- Include safe inputs, prohibited inputs, human review role, and output format when relevant.
- Keep Gemini-first and platform-agnostic.
- Make artifacts concise enough to use under time pressure.
- Make artifacts auditable: assumptions, owner, date, reviewer, and source should be easy to capture.

## Recommended artifact structure

Use this structure unless another format is clearly better:

```text
# [Artifact Name]

## Purpose

## When to use

## Safe inputs

## Prohibited inputs

## Workflow or template

## Human review checklist

## Migration notes
```

## Tone and positioning

Write in a conservative, credible PM/Ops voice:

- Practical
- Specific
- Audit-friendly
- Non-hype
- Clear about uncertainty
- Respectful of existing processes
- Focused on reporting quality, project integrity, schedule/accounting reconciliation, risk/issue/action discipline, and knowledge capture

## Completion checklist

Before considering an artifact done, confirm:

- It is safe for personal/pre-start use.
- It does not imply access Tom may not have yet.
- It does not request or expose sensitive data.
- It has a clear human review step.
- It can work manually or in Gemini Enterprise.
- It could later migrate to approved employer tooling.
