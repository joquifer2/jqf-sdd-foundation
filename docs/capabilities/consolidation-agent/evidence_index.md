# Indice de evidencias - Consolidation Agent

## Proposito

Este documento indexa evidencia historica, decisiones y validaciones relacionadas con el MVP Development de `Consolidation Agent`.

No es baseline canonico por si mismo y no autoriza Development adicional, runtime, scripts, workflows, tools, reorganizacion fisica ni cambios sobre baselines cerrados.

---

## Metadatos

| Campo | Valor |
| --- | --- |
| Capacidad | Consolidation Agent |
| SDD Mode | SDD Full |
| Responsable | Jordi Quiroga |
| Ultima actualizacion | 2026-08-02 |
| Handover relacionado | `docs/capabilities/consolidation-agent/closure_handover.md` |
| Specification relacionada | `specs/capabilities/consolidation-agent/spec-001-consolidation-agent.md` |
| Architecture relacionada | `specs/capabilities/consolidation-agent/arch-001-consolidation-agent.md` |

---

## Evidencias

| ID evidencia | Tipo de evidencia | Fuente | Artefacto relacionado | Estado | Notas |
| --- | --- | --- | --- | --- | --- |
| CA-EV-001 | Decision | Decision humana del 2026-08-02 | `docs/capabilities/consolidation-agent/tasks.md` | Verificado | Autoriza Development solo para MVP dentro de SPEC/ARCH/Task Plan. |
| CA-EV-002 | Gate | QA Gate T-011 | `docs/capabilities/consolidation-agent/tasks.md`; `docs/capabilities/consolidation-agent/sdd_readiness_assessment.md` | Verificado | Architecture paso con condiciones menores; Development requeria autorizacion posterior. |
| CA-EV-003 | Revision | Reviewer del plan posterior a Architecture | `docs/capabilities/consolidation-agent/tasks.md` | Verificado | Plan aprobado tras correcciones menores. |
| CA-EV-004 | Implementacion documental | Definicion canonica creada | `.github/agents/consolidation.agent.md` | Verificado | Agente metodologico, no operativo; no crea runtime ni automatizacion. |
| CA-EV-005 | Implementacion documental | Adaptador Codex creado | `.codex/agents/consolidation.toml` | Verificado | Adaptador subordinado a la definicion canonica. |
| CA-EV-006 | Catalogo | Routing actualizado | `AGENTS.md`; `.github/instructions/sdd.instructions.md`; `.github/agents/README.md`; `.codex/agents/README.md` | Verificado | Registra disponibilidad del agente sin sustituir validacion humana. |
| CA-EV-007 | Catalogo | Indices de capacidad actualizados | `docs/capabilities/index.md`; `specs/capabilities/index.md` | Verificado | Indices no normativos; solo routing y trazabilidad. |
| CA-EV-008 | Validacion | Validacion estatica | Workspace local | Verificado | Sin scripts, tools, workflows, runtime, consolidaciones reales, movimientos fisicos ni cambios a baselines cerrados. |
| CA-EV-009 | Validacion | Validacion retrospectiva SDD Modes | `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/consolidation_report.md`; `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/validation_closure.md`; `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/qa_gate_decision.md` | Closed with conditions / PASS WITH CONDITIONS | Validacion funcional cerrada; no se modifico SDD Modes ni se inicio Repository Physical Normalization. |
| CA-EV-010 | Expediente de validacion | Paquete completo SDD Modes retrospective | docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/validation_handover.md; docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/evidence_index.md; docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/residual_debt_and_reentry.md; docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/validation_closure.md; docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/qa_gate_decision.md | Cerrado con condiciones | Paquete autocontenido para Reviewer/QA y reentrada futura; no es baseline de SDD Modes. |
| CA-EV-011 | Gate | Global Closure Coherence Gate | docs/capabilities/consolidation-agent/global_closure_coherence_gate.md | PASS WITH CONDITIONS | Cierra la coherencia global del expediente actualizado; no autoriza Development ni normalizacion fisica. |

---

## Fuentes solo de descubrimiento

| Fuente | Motivo de conservacion | Restricciones |
| --- | --- | --- |
| N/A | N/A | N/A |

---

## Evidencia sustituida o superada

| Artefacto o evidencia | Sustituido por | Motivo | Conservar para auditoria |
| --- | --- | --- | --- |
| QA T-035 inicial `Blocked` | Decision humana de Development del 2026-08-02 y reevaluacion posterior | El bloqueo era falta de autorizacion humana; fue resuelto por decision explicita. | Si |
| Resultado preparatorio anterior de la retrospectiva SDD Modes | `qa_gate_decision.md` y `validation_closure.md` del expediente retrospectivo | La validacion local fue completada, revisada y evaluada por QA con `PASS WITH CONDITIONS`; el estado preparatorio queda superado. | Si |

---

## Guia de carga de evidencia

Para revisar o cerrar esta capacidad, cargar por defecto:

1. `docs/capabilities/consolidation-agent/closure_handover.md`.
2. `docs/capabilities/consolidation-agent/residual_debt.md`.
3. Este `evidence_index.md`.
4. `SPEC-001` y `ARCH-001` de la capacidad.
5. `.github/agents/consolidation.agent.md` y `.codex/agents/consolidation.toml`.
6. `docs/capabilities/consolidation-agent/validations/sdd-modes-retrospective/validation_closure.md` y `qa_gate_decision.md` si se revisa la validacion funcional.`r`n7. `docs/capabilities/consolidation-agent/global_closure_coherence_gate.md` para el gate final de coherencia global.

Cargar los expedientes cerrados relacionados solo para auditoria, reentrada o validacion especifica.