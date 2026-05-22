# AI_TOOL_APPROVAL_STRATEGY.md

## Purpose

A practical, conservative strategy for moving an AI-enabled PM/Ops use case from idea to approved workflow, designed for a federal/defense-adjacent environment where employer AI policy may be unknown or evolving at the time the use case is identified.

The strategy is Gemini-first but platform-agnostic. It is written so that a future ATLAS workflow or prompt can reference this file for the approval pattern instead of re-inventing one.

This file does not state employer policy and does not authorize any specific tool or data path. It is personal preparation material. Any step that touches employer data requires explicit employer approval.

## Where this fits

- `AI_GOVERNANCE_NOTES.md` defines the posture and the boundary.
- `DATA_SENSITIVITY_DECISION_MODEL.md` classifies a candidate input and routes it to a tool environment.
- `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` defines what a human review point looks like.
- This file is the end-to-end approval pattern that ties them together for a single candidate use case.

## Approval pattern (six steps)

1. Identify a candidate AI use case.
2. Classify the data path.
3. Identify the approved tool environment.
4. Define the human review point.
5. Pilot safely with synthetic or sanitized examples.
6. Document benefits, limitations, and residual risks; request approval; record the decision.

Each step has explicit "do" and "do not" content below.

## Step 1 - Identify a candidate AI use case

Look for PM/Ops work where AI can plausibly help quality, speed, consistency, or completeness without replacing accountable judgment. Strong candidate signals:

- Repeatable structure (the same kind of output is produced often).
- Clear inputs (the source material is well-defined).
- Clear human reviewer (someone is already accountable for the output).
- Reversibility (a wrong AI output can be caught and corrected before harm).
- Synthetic equivalent exists (a fictional version of the task can be built without employer data).

Weak signals - reconsider before continuing:

- The task is judgment-dense and the AI output would be hard to second-guess.
- The output would go directly to a customer, leadership, or an auditable system without a defined review.
- There is no synthetic version (so it is impossible to pilot safely).
- The task already has an approved non-AI process that is working well.

Anti-patterns to reject outright:

- "Let AI decide" tasks (approvals, escalations, scoring people).
- "Speed up" tasks where the speed gain comes from skipping review.
- "Just summarize this restricted document" tasks.

## Step 2 - Classify the data path

Use `DATA_SENSITIVITY_DECISION_MODEL.md` to classify the inputs and the intended output.

Capture, for each candidate use case:

- **Input category.** Synthetic, public, Tom-personal, employer-approved, or prohibited.
- **Output category.** Same options. Note that a synthetic input can produce an output that is treated as employer-approved once it is reviewed and adopted inside the employer environment.
- **Storage path.** Where the input lives, where the AI tool sees it, where the output is saved.
- **Transmission path.** Whether data crosses any tool, account, or network boundary that is not approved.

If any element of the data path crosses into "prohibited" or "uncertain", stop. The use case is not ready for AI in its current form. Options: redesign the use case to use synthetic-only inputs, wait for tool approval, or drop the candidate.

## Step 3 - Identify the approved tool environment

Match the data category to an approved environment:

- **Synthetic or public.** Any personal or employer tool, including ATLAS-local Markdown work.
- **Tom-personal.** Tom's personal tools only; never inside an employer system as if it were employer content.
- **Employer-approved.** Only inside the specific employer-approved AI environment for that data category. Gemini Enterprise (if approved for that data) is the assumed first option; otherwise the employer-named alternative.
- **Prohibited.** No AI tool. Reconsider whether AI is the right approach at all.

Do not assume a tool is approved for a data category because the tool is approved generally. Approval is a tool + data + context decision. When in doubt, treat as not approved.

Do not assume the absence of a "no" is a "yes." If employer policy on a tool and data combination is unknown, treat it as unapproved until confirmed.

## Step 4 - Define the human review point

For the candidate use case, write down:

- Who is the accountable reviewer (named role, not "AI").
- What they review (the AI output, the source, the diff against a prior version, etc.).
- What "good" and "bad" look like, in one or two sentences each.
- What the reviewer does when the output is bad (edit, reject, escalate).
- How the review is recorded (sign-off in the doc, comment, log entry).
- Whether the review is mandatory before every use or sampled for spot-checks.

Use the patterns in `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`. Workflows without a defined human review point are not ready to pilot.

## Step 5 - Pilot safely

Always pilot before going live with employer data.

- Build a synthetic version of the task (`08_SYNTHETIC_DEMOS/` is the right place for this in ATLAS).
- Run the workflow end-to-end on synthetic data, including the human review step.
- Note where the AI tool helped, where it added noise, and where it was misleading.
- If the use case requires sanitized real data, route the sanitization through an approved process and an approved tool; do not improvise.
- Time-box the pilot. Decide in advance how many runs constitute "enough" to evaluate.

A failed pilot is a success: it told you something before any real data was exposed.

## Step 6 - Document, request approval, record the decision

Before any real data flows through the workflow, write a short approval brief covering:

- **Use case.** One paragraph on what the workflow does and why.
- **Data path.** Inputs, outputs, storage, transmission, and the data category for each.
- **Tool.** Which approved tool, in which environment, with which account.
- **Human review.** Reviewer, criteria, recording.
- **Benefits.** What improves (quality, consistency, speed, completeness).
- **Limitations.** Where the AI tool is unreliable or unverified.
- **Residual risks.** What could still go wrong, even with the controls in place.
- **Stop conditions.** What would cause you to pause or retire the workflow.
- **Approver.** The named person whose approval is required for this combination of tool, data category, and use case.

Once approved (or rejected), record the decision in the appropriate venue inside the employer environment. In ATLAS personal preparation, mirror the decision in `10_DECISION_LOG/DECISION_LOG.md` with employer-sensitive details redacted.

## What to avoid

- Approval by inertia: "no one said no, so it must be fine."
- Approval by capability: "the tool can do this, so we can use it."
- Approval by analogy: "team X uses tool Y for thing Z, so I can too."
- Verbal-only approval that nobody can find later.
- Pilots that skip the human review step "just to see what the AI can do" using real data.
- Migrating a personal preparation workflow into an employer tool without re-running steps 2, 3, 4, and 6 for the new environment.

## Triggers for re-approval

Re-run the approval pattern when any of the following change:

- The data category of the input or output.
- The tool, account, or environment.
- The accountable human reviewer.
- The criteria for "good" and "bad" output.
- Employer policy on the tool or data category.

Treat re-approval as cheap. Treat skipped re-approval as expensive.

## Lightweight intake template

Use this template (or its equivalent inside the approved employer environment) when proposing a new candidate.

```text
Candidate use case:
[One paragraph]

Inputs (with data category):
- ...

Outputs (with data category):
- ...

Storage path:
- Input lives in: ...
- AI tool sees it in: ...
- Output is saved in: ...

Transmission path:
- ...

Proposed tool and environment:
- ...

Human review point:
- Reviewer:
- What they review:
- "Good" criteria:
- "Bad" criteria:
- Recording:

Pilot plan:
- Synthetic data source:
- Number of runs:
- Evaluation criteria:

Benefits:
- ...

Limitations and residual risks:
- ...

Stop conditions:
- ...

Approver:
- ...
```

Keep the brief short enough to actually use. Long approval documents that nobody reads do not improve safety.
