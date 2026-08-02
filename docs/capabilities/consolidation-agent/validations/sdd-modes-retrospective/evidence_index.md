# Evidence Index - SDD Modes Retrospective Consolidation Validation

## Purpose

This index lists the evidence used by the first official functional validation of `Consolidation Agent` on the closed `SDD Modes` capability.

It is not a canonical baseline for `SDD Modes` and does not modify closed artifacts.

## Validation Metadata

| Field | Value |
| --- | --- |
| Validation package | `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/` |
| Main report | `consolidation_report.md` |
| Mode | `proposal-only` |
| Target | `SDD Modes` |
| Date | 2026-08-02 |

## Primary Evidence

| ID | Artifact | Role | Status | Use in validation |
| --- | --- | --- | --- | --- |
| EV-SM-001 | `docs/project_brief.md` | Initial scope and SDD Full declaration | Closed input | Establish target purpose, limits and original governance mode. |
| EV-SM-002 | `docs/context_refs.md` | Context index and baseline list | Closed input | Identify canonical baseline, validation candidates, discovery-only sources and pending debt. |
| EV-SM-003 | `docs/tasks.md` | Decision and task log | Closed input | Reconstruct T-001..T-027, final closure decision and VAL states. |
| EV-SM-004 | `docs/sdd_readiness_assessment.md` | Gate/readiness evidence | Closed input | Confirm `Completed with conditions`, `PASS WITH CONDITIONS`, final baseline and re-entry. |
| EV-SM-005 | `specs/spec-001-sdd-modes.md` | Normative specification | Final | Confirm semantics, requirements, validation scenarios and VAL-001 treatment. |
| EV-SM-006 | `specs/spec-001-sdd-modes.architecture.md` | Conceptual/documentary architecture | Final | Confirm architecture decisions, artifact roles and open lifecycle questions. |

## Methodology Evidence

| ID | Artifact | Role | Status | Use in validation |
| --- | --- | --- | --- | --- |
| EV-MET-001 | `docs/capabilities/project-consolidation-and-closure/closure_handover.md` | Closure methodology handover | Closed | Establish consolidation/closure boundaries and physical normalization debt RD-003/RD-004. |
| EV-MET-002 | `docs/capabilities/project-consolidation-and-closure/residual_debt.md` | Residual debt register | Closed / active debt | Confirm that physical normalization and SDD Modes packaging were intentionally deferred. |
| EV-MET-003 | `docs/capabilities/project-consolidation-and-closure/evidence_index.md` | Evidence index | Closed | Confirm context role of SDD Modes and closure evidence practice. |
| EV-MET-004 | `docs/capabilities/foundation-derivation-and-project-initialization/closure_handover.md` | Derivation/initialization handover | Closed | Confirm baseline/export boundary and future status of Repository Physical Normalization. |
| EV-MET-005 | `docs/capabilities/foundation-derivation-and-project-initialization/residual_debt.md` | Residual debt register | Closed / active debt | Confirm FDR-RES-002/FDR-RES-007 as future physical normalization debts. |

## Consolidation Agent Evidence

| ID | Artifact | Role | Status | Use in validation |
| --- | --- | --- | --- | --- |
| EV-CA-001 | `.github/agents/consolidation.agent.md` | Canonical agent definition | Closed with conditions | Confirm allowed outputs, forbidden actions, workflow and proposal-only boundaries. |
| EV-CA-002 | `.codex/agents/consolidation.toml` | Codex adapter | Closed with conditions | Confirm adapter remains subordinate to canonical agent definition. |
| EV-CA-003 | `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md` | Agent specification | Final | Confirm inputs, outputs, requirements, errors and limits. |
| EV-CA-004 | `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md` | Agent architecture | Final | Confirm report structure, components and physical proposal builder. |
| EV-CA-005 | `docs/capabilities/consolidation-agent/tasks.md` | Implementation task plan and closure record | Closed with conditions | Confirm MVP scope, validation task T-030 and no further Development authorization. |
| EV-CA-006 | `docs/capabilities/consolidation-agent/closure_handover.md` | Agent closure handover | Closed with conditions | Confirm residual debt and re-entry points for future consolidations. |
| EV-CA-007 | `docs/capabilities/consolidation-agent/residual_debt.md` | Agent residual debt | Closed with conditions | Confirm standalone report template and automation remain future debt. |

## Validation Package Evidence

| ID | Artifact | Role | Status | Use in validation |
| --- | --- | --- | --- | --- |
| EV-VAL-001 | `consolidation_report.md` | Main validation report | Closed with conditions | Reconstruct retrospective consolidation result, inventory, debt, re-entry and physical proposal. |
| EV-VAL-002 | `residual_debt_and_reentry.md` | Validation debt and re-entry register | Closed with conditions | Preserve conditions, recommendations and future routes. |
| EV-VAL-003 | `validation_handover.md` | Validation handover | Closed with conditions | Provide low-context entrypoint for review, QA and future re-entry. |
| EV-VAL-004 | `qa_gate_decision.md` | Final QA Gate decision | PASS WITH CONDITIONS | Establish functional validation decision and conditions. |
| EV-VAL-005 | `validation_closure.md` | Formal documentary closure | Closed with conditions | Close the local validation package without modifying SDD Modes. |
## Global Routing Evidence

| ID | Artifact | Role | Status | Use in validation |
| --- | --- | --- | --- | --- |
| EV-GLOB-001 | `docs/capabilities/index.md` | Capability index | Current | Confirm discoverability of SDD Modes and Consolidation Agent. |
| EV-GLOB-002 | `specs/capabilities/index.md` | Specification index | Current | Confirm final spec/architecture registration. |
| EV-GLOB-003 | `AGENTS.md` | Agent catalog and repository guidance | Current | Confirm Consolidation Agent placement and SDD Harness boundaries. |
| EV-GLOB-004 | `.github/instructions/sdd.instructions.md` | SDD instructions | Current | Confirm Consolidation/Closed phases, SDD Modes and restrictions. |

## Evidence Boundaries

| Boundary | Treatment |
| --- | --- |
| Closed SDD Modes baseline | Read-only; no mutation. |
| Discovery-only external sources | Not promoted to normative status. |
| Repository Physical Normalization | Proposed only; no action taken. |
| Git history | Secondary evidence, not a substitute for decisions, gates or approvals. |
| This validation package | Closed local evidence of Consolidation Agent validation, not an official SDD Modes re-closure. |