# atlas-planner Skill

## Purpose

Use this skill to plan ATLAS PM/Ops OS work without restarting from scratch or overbuilding. It converts the current context, roadmap, and backlog into a focused next set of actions.

## When to use

Use this skill when:

- Starting a new ATLAS work session
- Choosing the next phase or artifact
- Prioritizing backlog items
- Breaking a broad request into manageable PM/Ops artifacts
- Checking whether a proposed build is too technical, too speculative, or unsafe

## Required source files

Read in this order:

1. `00_MASTER_CONTEXT/MASTER_CONTEXT.md`
2. `09_HANDOFFS/SESSION_HANDOFF.md`
3. `01_MASTER_PLAN/MASTER_PLAN.md`
4. `02_ROADMAP/ROADMAP.md`
5. `03_BACKLOG/ARTIFACT_BACKLOG.md`

## Planning rules

- Preserve the safety boundary at all times.
- Do not assume employer-specific details.
- Prefer the smallest useful next artifact.
- Keep outputs Markdown-first.
- Do not introduce code, apps, APIs, databases, deployments, or package dependencies unless explicitly requested later.
- Prioritize artifacts that help Tom provide credible PM/Ops value during clearance-limited onboarding.
- Treat AI integration as a major value area, but keep it practical and governance-aware.

## Output format

When using this skill, produce:

1. Current phase confirmation
2. Recommended next artifact
3. Why it matters
4. Required source files
5. Proposed edits or new file paths
6. Safety considerations
7. Definition of done
8. Handoff update reminder

## Quality checks

Before finalizing a plan, confirm:

- The plan does not require real employer data.
- The plan fits the current phase or explicitly justifies phase movement.
- The plan improves PM/Ops outcomes.
- The plan can be executed with Gemini or manually.
- The plan preserves a migration path to approved employer systems.
