# Referencias de contexto - Repository Physical Normalization

> Este documento indexa el contexto vigente para la capacidad `Repository Physical Normalization` tras la ejecucion y cierre de `DEV-RPN-010`.
>
> No autoriza Development adicional, movimientos nuevos, retirada de stubs, scripts, workflows ni automatizaciones.

---

## 1. Identidad

```yaml
proyecto:
  nombre: JQF SDD Foundation - Repository Physical Normalization
  id_proyecto: repository-physical-normalization
  tipo_proyecto: foundation-repository-governance
  estado: Closed with minor conditions
  fecha_creacion: 2026-08-02
  ultima_actualizacion: 2026-08-02
  responsable: Jordi Quiroga

sdd_mode:
  modo_declarado: SDD Full
  fuente_canonica: docs/capabilities/repository-physical-normalization/project_brief.md
  estado: Verificado
```

---

## 2. Estado Real Post-Development

| Elemento | Estado vigente |
| --- | --- |
| DEV-RPN-010 | Closed |
| T-001 a T-039 | Completed |
| Siguiente paso dentro de DEV-RPN-010 | None |
| Siguiente accion valida | None; future reentry requires explicit human decision |
| Gate global | PASS WITH MINOR CONDITIONS - T-040 |
| Development adicional | NOT AUTHORIZED |
| Movimientos adicionales | NOT AUTHORIZED |
| Scripts, workflows o automatizaciones | NOT AUTHORIZED |

---

## 3. Baseline Fisico Vigente

| Ambito | Ruta | Clasificacion | Estado |
| --- | --- | --- | --- |
| SDD Modes Specification | `specs/capabilities/sdd-modes/spec-001-sdd-modes.md` | Canonical capability-local baseline | Vigente |
| SDD Modes Architecture | `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` | Canonical capability-local baseline | Vigente |
| Expediente SDD Modes | `docs/capabilities/sdd-modes/` | Canonical capability-local dossier | Vigente |
| Root SDD Modes Specification | `specs/spec-001-sdd-modes.md` | Temporary compatibility stub | No normativo |
| Root SDD Modes Architecture | `specs/spec-001-sdd-modes.architecture.md` | Temporary compatibility stub | No normativo |
| Root SDD Modes dossier docs | `docs/project_brief.md`; `docs/context_refs.md`; `docs/tasks.md`; `docs/sdd_readiness_assessment.md` | Temporary compatibility stubs | No normativos |

El contenido normativo de SDD Modes no fue modificado por la normalizacion fisica. Las rutas raiz se conservan solo para compatibilidad y trazabilidad de referencias historicas o externas.

---

## 4. Artefactos Principales de Repository Physical Normalization

| Artefacto | Funcion | Estado |
| --- | --- | --- |
| `docs/capabilities/repository-physical-normalization/project_brief.md` | Brief y decisiones humanas de la capacidad. | Closed with minor conditions |
| `specs/capabilities/repository-physical-normalization/spec-001-repository-physical-normalization.md` | Specification normativa de la capacidad. | Baseline de capacidad |
| `specs/capabilities/repository-physical-normalization/arch-001-repository-physical-normalization.md` | Architecture documental de la capacidad. | Completed |
| `docs/capabilities/repository-physical-normalization/tasks.md` | Task Plan T-001 a T-041. | T-001..T-040 completed; T-041 pending human decision |
| `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md` | Readiness reconciliado post-Development. | PASS WITH MINOR CONDITIONS - T-040 |
| `docs/capabilities/repository-physical-normalization/evidence_index.md` | Indice de evidencias de ejecucion, gates y garantias negativas. | Created |
| `docs/capabilities/repository-physical-normalization/residual_debt.md` | Deuda residual aceptada y punto de reentrada. | Created |
| `docs/capabilities/repository-physical-normalization/closure_handover.md` | Handover para cierre global y reentrada futura. | Updated |
| `docs/capabilities/repository-physical-normalization/global_closure_gate.md` | Decision QA Gate T-040. | PASS WITH MINOR CONDITIONS |

---

## 5. Paquete Governed Execution Preparation

| Artefacto | Funcion | Estado vigente |
| --- | --- | --- |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/README.md` | Indice del paquete GEP. | Closed - DEV-RPN-010 |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/canonical_route_registry.md` | Registro de rutas canonicas y legacy. | Closed - DEV-RPN-010 |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/reference_map.md` | Mapa de referencias activas, historicas y compatibilidad. | Closed - DEV-RPN-010 |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_plan.md` | Plan y resultado de movimientos autorizados. | Closed - DEV-RPN-010 |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/compatibility_plan.md` | Plan de stubs, referencias y derivados. | Closed - DEV-RPN-010 |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/rollback_plan.md` | Rollback viable de DEV-RPN-010. | Closed - DEV-RPN-010 |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/validation_checklist.md` | Evidencia de QA y validation checks. | Closed - DEV-RPN-010 |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/sdd_modes_pilot_package.md` | Aplicacion piloto sobre SDD Modes. | Closed - DEV-RPN-010 |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/movement_execution_report.md` | Reporte de ejecucion fisica autorizada. | Closed - DEV-RPN-010 |
| `docs/capabilities/repository-physical-normalization/governed-execution-preparation/sdd_modes_architecture_route_decision.md` | Decision Option A aplicada en DEV-RPN-010. | Closed - DEV-RPN-010 |

---

## 6. Gates y Decisiones

| Tarea | Decision | Resultado vigente |
| --- | --- | --- |
| T-006 | Reviewer Specification | Approved with minor changes |
| T-007 | QA Gate Specification | Pass with minor conditions |
| T-008 | Decision humana Architecture | Authorized |
| T-011 | Reviewer Architecture | Approved with minor changes |
| T-012 | QA Gate Architecture | Pass with minor conditions |
| T-013 | Decision humana GEP | Authorized |
| T-021 | Reviewer GEP | Approved with minor changes |
| T-022 | QA Gate GEP | Pass with minor conditions |
| T-023 | Decision humana Development | Authorized |
| T-027 | Reviewer primera ola Development | Approved with minor changes |
| T-028 | QA Gate primera ola Development | Pass with minor conditions |
| T-033 | Reviewer DEV-RPN-010 package | Approved with minor changes |
| T-034 | QA Gate DEV-RPN-010 package | Pass with minor conditions |
| T-035 | Decision humana DEV-RPN-010 | Authorized |
| T-037 | Reviewer DEV-RPN-010 execution | Approved with minor changes |
| T-038 | QA Gate DEV-RPN-010 execution | Pass with minor conditions |
| T-039 | Decision humana closure DEV-RPN-010 | Closed |
| T-040 | Global Closure Gate | Pass with minor conditions |
| T-041 | Human global closure decision | Closed |

---

## 7. Proyectos y Capacidades Relacionadas

| Capacidad | Relacion | Estado | Fuentes canonicas vigentes |
| --- | --- | --- | --- |
| SDD Modes | Primer caso real aplicado por RPN. | Closed with conditions / physically normalized | `docs/capabilities/sdd-modes/`; `specs/capabilities/sdd-modes/spec-001-sdd-modes.md`; `specs/capabilities/sdd-modes/arch-001-sdd-modes.md` |
| SDD Project Consolidation and Closure | Define categorias de cierre, handover, evidencia, deuda y reentrada. | Closed | `docs/capabilities/project-consolidation-and-closure/closure_handover.md` |
| Foundation Derivation and Project Initialization | Define limites con repositorios derivados. | Closed | `docs/capabilities/foundation-derivation-and-project-initialization/closure_handover.md` |
| Consolidation Agent | Produce propuestas `proposal-only`; no ejecuta normalizacion fisica. | Closed with conditions | `docs/capabilities/consolidation-agent/closure_handover.md` |

---

## 8. Reglas de Carga de Contexto

Antes de revisar o validar el cierre global de esta capacidad, cargar:

1. `docs/capabilities/repository-physical-normalization/project_brief.md`.
2. `docs/capabilities/repository-physical-normalization/context_refs.md`.
3. `docs/capabilities/repository-physical-normalization/sdd_readiness_assessment.md`.
4. `docs/capabilities/repository-physical-normalization/tasks.md`.
5. `docs/capabilities/repository-physical-normalization/evidence_index.md`.
6. `docs/capabilities/repository-physical-normalization/residual_debt.md`.
7. `docs/capabilities/repository-physical-normalization/closure_handover.md`.
8. El paquete GEP cuando se necesite evidencia detallada de DEV-RPN-010.

No cargar rutas raiz de SDD Modes como normativas. Las rutas raiz son `Temporary compatibility stubs`.

---

## 9. Deuda Residual y Reentrada

La deuda residual aceptada para cierre es la permanencia temporal de stubs raiz y referencias historicas cubiertas por compatibilidad. Su retirada futura requiere una nueva reentrada con:

- auditoria de referencias activas;
- analisis de impacto en repositorios derivados;
- plan de retirada o movimiento;
- compatibility plan actualizado;
- rollback plan actualizado;
- Reviewer Agent;
- QA Gate Agent;
- autorizacion humana explicita.

---

## 10. Restricciones Vigentes

- No eliminar stubs.
- No ejecutar movimientos nuevos.
- No modificar contenido normativo de SDD Modes.
- No autorizar Development adicional.
- No iniciar Project Initializer.
- No iniciar Derived Repository Upgrade and Migration.
- No crear scripts, herramientas, workflows ni automatizaciones.

---

## 11. Siguiente Accion Valida

```text
No active next step. Repository Physical Normalization is Closed with minor conditions.
```

QA Gate T-040:

```text
PASS WITH MINOR CONDITIONS
```