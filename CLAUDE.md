# CLAUDE.md - ATLAS PM/Ops OS

Repo-level operating instructions for Claude Code. These apply alongside the user's global `CLAUDE.md` and the ATLAS source-of-truth files. They are loaded automatically whenever a session runs in this working directory.

## Source-of-truth files (read in this order)

1. `README.md` - project identity, purpose, folder map.
2. `00_MASTER_CONTEXT/MASTER_CONTEXT.md` - durable identity, safety boundary, posture, phase list, session-start and session-end protocols, precedence rule.
3. `09_HANDOFFS/SESSION_HANDOFF.md` - current status, decisions, open items, next best prompt.
4. The named phase prompt under `05_PROMPTS/PHASE_PROMPTS/` for the current phase.
5. `02_ROADMAP/ROADMAP.md` for per-phase detail and `03_BACKLOG/ARTIFACT_BACKLOG.md` for per-artifact fields.
6. `10_DECISION_LOG/DECISION_LOG.md` for active decisions and historical rationale.

If `MASTER_CONTEXT.md` and `SESSION_HANDOFF.md` disagree, `MASTER_CONTEXT.md` wins on durable identity and safety; `SESSION_HANDOFF.md` wins on current status and next best prompt; `ROADMAP.md` is authoritative for per-phase detail; `ARTIFACT_BACKLOG.md` is authoritative for per-artifact fields.

## Safety boundary (one line)

Use only synthetic, public, generic, fictional, or Tom-authored non-proprietary material. Do not use classified, CUI, ITAR or export-controlled, proprietary, customer, contract, internal schedule, internal finance, internal technical, real meeting note, real Microsoft Project, or real project accounting data.

## What not to add

Do not add apps, package dependencies, APIs, databases, deployment files, frontend code, backend code, or other code scaffolding unless the active phase prompt explicitly requests it. Keep every artifact Markdown-first, Gemini-first, and platform-agnostic.

The single authorized exception is `.github/workflows/codex-review-loop.yml`, added to support the Standing Codex review loop. Authorized in D-0022. Any further CI files require a new logged decision.

## Standing Codex review loop

The repo has two layers of automation for Codex review feedback:

- **CI layer:** `.github/workflows/codex-review-loop.yml` runs Claude Code on every PR review submitted by `chatgpt-codex-connector`, on every per-line review comment from that bot, and on any comment that mentions `@claude`. The workflow requires a repo secret (`ANTHROPIC_API_KEY` or `CLAUDE_CODE_OAUTH_TOKEN`). See D-0022 for the authorization of this CI exception.
- **Interactive layer (this file):** Whenever a Claude Code session is running locally in this repo and a PR has unresolved Codex review threads, address them automatically per the loop below.

Apply the following loop in both layers, without asking permission, on every session and after every push to a PR branch:

1. **Detect.** Run `gh pr view <PR#> --json url,number,reviewThreads` (or the GraphQL equivalent) to list threads. If `<PR#>` is omitted, GitHub CLI resolves it from the current branch.
2. **Triage each unresolved thread.** For each thread, either:
   - Apply the requested change in the named file and line, or
   - Reply on the thread explaining why not. Valid reasons: the change would violate the ATLAS safety boundary, conflict with an Active decision in `10_DECISION_LOG/DECISION_LOG.md`, break a global guardrail in `C:\Users\thalf\.claude\CLAUDE.md`, or fall outside the active phase's scope.
3. **Commit.** Use Conventional Commits on the PR's existing branch, scoped to the phase or chore. Example: `docs(phase-02): address codex review on PR #N` or `chore(codex-review): clarify branch policy`.
4. **Push.** Push to the same branch. Use `git push` for fast-forward updates; only use `--force-with-lease` on the PR's own branch and only when a rebase requires it. Never `--force-push` a shared branch.
5. **Resolve threads.** Mark each addressed thread resolved via `gh api graphql` or the PR UI so the review state stays clean.
6. **Log decisions.** If any thread produced a durable decision (new rule, new posture, new constraint), append an entry to `10_DECISION_LOG/DECISION_LOG.md` in the same session.
7. **Update the handoff.** If the round changes phase state, the next best prompt, or any open item, update `09_HANDOFFS/SESSION_HANDOFF.md` before stopping.

Hard limits that never get overridden by review feedback:

- Never edit `main`, `master`, `release`, or `prod` directly.
- Never `git push --force` on a shared branch.
- Never skip hooks (`--no-verify`, `--no-gpg-sign`, etc.) unless the user explicitly requests it.
- Never apply a change that would commit employer-sensitive material into this personal repo.
- Never apply a change that violates the ATLAS hard safety boundary or the global guardrails in the user's `CLAUDE.md`.

## Commit and branch policy

- Feature branch per ATLAS phase: `feat/phase-NN-<short-slug>`.
- Cross-cutting operating changes (rules, automations, repo config): `chore/<short-slug>`.
- Conventional Commits, imperative present tense. Example scopes: `docs(phase-02)`, `chore(codex-review)`, `chore(repo-config)`.
- Open a PR against `main` for every branch. Stack a phase branch on top of a still-open phase branch only when the new phase depends on the prior phase's content; rebase onto `main` after the prior PR merges.

## Session-end protocol (summary)

The full protocol is in `MASTER_CONTEXT.md`. The repo-scoped summary:

1. Update `09_HANDOFFS/SESSION_HANDOFF.md` using `09_HANDOFFS/SESSION_HANDOFF_TEMPLATE.md`.
2. Log any durable decisions in `10_DECISION_LOG/DECISION_LOG.md` in the same session; do not defer.
3. Confirm no employer-sensitive material entered any file or chat transcript.
4. Local-agent mode: commit on a feature or chore branch using Conventional Commits. Chat-only mode: hand the user the exact files, paths, and a suggested Conventional Commits message.

## When to update this file

Edit `CLAUDE.md` when:

- A new repo-scoped operating rule is added (new automation, new branch convention, new safety constraint).
- A source-of-truth file is added or renamed.
- The Codex review loop changes (different review tool, different commit convention, different resolution mechanism).

Log every `CLAUDE.md` change in `10_DECISION_LOG/DECISION_LOG.md` so the operating rules and the decision log stay synchronized.
