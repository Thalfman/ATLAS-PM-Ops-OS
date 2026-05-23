# SYNTHETIC_DEMO_PACK.md

**SYNTHETIC DEMO PACK. EVERY FILE IN THIS DIRECTORY IS FICTIONAL. NOT MOTOROLA SOLUTIONS, NOT ANY REAL PROGRAM, CUSTOMER, OR CONTRACT.**

## Pack identity

- **Phase:** 7 - Synthetic Demo Pack
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23
- **Shared scenario:** `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`

## Purpose

The Synthetic Demo Pack is the set of fictional, end-to-end demonstrations that prove ATLAS workflow value without any real employer data. Each demo pairs a Phase 4 workflow card (W-NN) with a Phase 5 prompt card (P-NN) against a synthetic input from the shared Project Northstar Demo scenario, walks the AI step, runs the human-review pattern from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, and produces a final output. Demos are patterns, not products; they never claim deployment-readiness.

## Pack rules (binding for every demo)

1. Every demo file opens with a bold synthetic label that names the fiction.
2. All names, dates, milestones, owners, risks, issues, and numbers are obvious fictions. No real program names, customer names, contract names.
3. Demos walk **input → AI step → human review → output** as a pattern. They are not finished products and not deployable artifacts.
4. Demos never blend in real data on the fly to "make it more realistic." That defeats the purpose.
5. Demos never claim deployment-readiness. Cross-references to W-NN / P-NN cards make the migration path explicit; nothing implies the demo itself is approved.
6. Demos cite the Phase 3 governance envelope by filename. The shared scenario file (`SYNTHETIC_PROJECT_SCENARIO.md`) publishes the envelope once; per-demo files repeat the four key lines for readability and do not restate policy.
7. The shared scenario is the single backdrop for the pack. Cross-demo references between demos (action IDs, milestone IDs, risk IDs) keep the pack coherent.

## Pack index

| File | Backlog A-ID | Paired W-NN | Paired P-NN | Per-domain review pattern |
|---|---|---|---|---|
| `SYNTHETIC_PROJECT_SCENARIO.md` | (utility, D-0048) | — | — | — |
| `SYNTHETIC_STATUS_PACK_DEMO.md` | A-0007 | W-01, W-12 | P-01, P-12 | Status and reporting outputs |
| `SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md` | A-0023 | W-05 | P-05 | Schedule outputs |
| `SYNTHETIC_ACTION_TRACKER_DEMO.md` | A-0024 | W-02, W-03 | P-02, P-03 | Meeting notes to action items |
| `SYNTHETIC_DISCREPANCY_TRIAGE_DEMO.md` | A-0051 | W-08 | P-08 | Risk and issue triage outputs |
| `SYNTHETIC_RISK_REGISTER_CLEANUP_DEMO.md` | A-0052 | W-07 | P-07 | Risk and issue triage outputs |

The Phase 7 prompt mentions several optional demo categories (EVM variance explanation, accounting reconciliation narrative, lessons learned, executive brief) that are not built in this pack. Rationale: A-0007 already covers the executive brief side through P-12; EVM and accounting reconciliation demos require synthetic finance workbooks that belong to Phase 9 (A-0054, A-0055, A-0056); the lessons-learned demo belongs to Phase 10 (A-0013, A-0058). Building those demos in Phase 7 would either duplicate Phase 9 / Phase 10 work or invent finance data without the supporting workbook. The pack's five demos cover the AI-drafting patterns that can stand on their own at Phase 7's level of fidelity; the rest is sequenced.

## Using a demo with a manager or peer

Per `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md` and `07_TEMPLATES/AI_INTEGRATION_DISCUSSION_GUIDE.md`:

1. State clearly, before opening the demo, that it is fictional and uses invented data.
2. Walk through the demo as a pattern (input → AI step → human review → output), not as a finished product.
3. Highlight the human review step explicitly.
4. Acknowledge the limits ("this is what it looks like on synthetic data; real data would need approvals and a different tool").
5. Stop on time.

Never blend in real data on the fly.

## Maintenance

- Demo file IDs follow the existing backlog A-IDs; append-only per D-0017.
- The shared scenario file is the source of truth for cast, milestones, workstreams. Schema changes apply to the scenario file first, then back-port relevant demos in the same session.
- Future demo additions for Phase 8+ (real schedule fidelity, EVM workbook fidelity, lessons-learned fidelity) follow the same per-demo file pattern and pair against the existing W-NN / P-NN catalog.
- Edits that would weaken the pack rules (paragraph 1-7 above) require a new logged decision before they can be accepted.

## Cross-references

- Shared scenario: `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.
- Workflow library index: `04_WORKFLOWS/WORKFLOW_LIBRARY.md`.
- Prompt library index: `05_PROMPTS/PROMPT_LIBRARY.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`, `AI_CONVERSATION_GUIDE.md`.
- Kit index (for in-conversation use): `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`; AI integration guide: `07_TEMPLATES/AI_INTEGRATION_DISCUSSION_GUIDE.md`.
- Backlog: `03_BACKLOG/ARTIFACT_BACKLOG.md` rows A-0007, A-0023, A-0024, A-0051, A-0052.
- Decision log: D-0045..D-0048 (Phase 7 set).
